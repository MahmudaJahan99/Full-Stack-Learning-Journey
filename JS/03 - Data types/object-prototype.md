# Prototypal Inheritance

JavaScript uses a **prototype-based object model**. Objects can inherit properties and methods from other objects through a mechanism called **prototypal inheritance**. This is different from the class-based inheritance model found in languages such as Java or C++. However, modern JavaScript also provides `class` syntax.

The important thing to understand is:

> **JavaScript's underlying inheritance mechanism is prototype-based.**

## What is a Prototype?

A **prototype** is an object that another object can use as a source of properties and methods.

For example:

```javascript
const person = {
  greet() {
    console.log("Hello!");
  },
};
```

Another object can use `person` as its prototype:

```javascript
const user = Object.create(person);

user.greet();
```

Output:

```text
Hello!
```

Notice that `user` itself does not contain a `greet` method. The method is found through its prototype.

## Prototype Chain

When JavaScript tries to access a property on an object, it first looks at the object itself. If the property is not found, JavaScript looks at the object's prototype. If it still cannot find the property, it continues through the **prototype chain**.

Example:

```javascript
const person = {
  greet() {
    console.log("Hello!");
  },
};

const user = Object.create(person);

user.greet();
```

The lookup can be visualized as:

```text
user
 |
 | "greet" not found here
 ↓
person
 |
 | "greet" found!
 ↓
greet()
```

The prototype relationship can continue through multiple levels. The final end of the ordinary object prototype chain is `null`.

Most objects created using object literals have a prototype connected to `Object.prototype`.

For example:

```javascript
const user = {
  name: "Jane",
};
```

Conceptually:

```text
user
  |
  ↓
Object.prototype
  |
  ↓
null
```

`Object.prototype` contains methods that are available to ordinary objects.

For example:

```javascript
const user = {
  name: "Jane",
};

console.log(user.toString());
```

The `user` object does not need to define its own `toString()` method. JavaScript can find it through the prototype chain.

```text
user
  |
  | toString() not found
  ↓
Object.prototype
  |
  | toString() found
  ↓
toString()
```

---

### Accessing an Object's Prototype

```javascript
Object.getPrototypeOf(user);
```

This returns the prototype of `user`.

Example:

```javascript
const user = {
  name: "Jane",
};

console.log(Object.getPrototypeOf(user));
```

For an ordinary object literal, this is related to:

```javascript
Object.prototype;
```

---

### `__proto__`

```javascript
user.__proto__;
```

This exposes the object's prototype through a legacy accessor.

For learning and modern code, prefer:

```javascript
Object.getPrototypeOf(user);
```

and:

```javascript
Object.setPrototypeOf(user, prototype);
```

when we specifically need to work with prototypes.

> `__proto__` is important to recognize because we will encounter it in JavaScript code and tutorials, but it is generally not the preferred API for manipulating prototypes.

---

## Prototypal Inheritance Example

Let's create a simple prototype:

```javascript
const animal = {
  eat() {
    console.log("Eating...");
  },
};
```

Now create another object based on it:

```javascript
const dog = Object.create(animal);
```

The `dog` object can access `eat()`:

```javascript
dog.eat();
```

Output:

```text
Eating...
```

The lookup works like this:

```text
dog
 |
 | eat() not found
 ↓
animal
 |
 | eat() found
 ↓
eat()
```

This is **prototypal inheritance**.

---

## Own Properties vs Inherited Properties

Consider:

```javascript
const animal = {
  eat() {
    console.log("Eating...");
  },
};

const dog = Object.create(animal);

dog.name = "Tommy";
```

The `dog` object has its own property:

```text
dog
 |
 ├── name → "Tommy"       ← Own property
 |
 └── Prototype
      |
      └── eat()           ← Inherited property
```

We can check whether a property belongs directly to the object:

```javascript
console.log(Object.hasOwn(dog, "name"));
```

Output:

```text
true
```

But:

```javascript
console.log(Object.hasOwn(dog, "eat"));
```

Output:

```text
false
```

`eat` is inherited from the prototype.

---

## Built-in Objects and Prototypes

Built-in objects also use prototypes.

For example:

```javascript
const numbers = [1, 2, 3];
```

Arrays have access to methods such as:

```javascript
numbers.push(4);
numbers.pop();
numbers.map(...);
numbers.filter(...);
```

These methods are provided through the array's prototype chain.

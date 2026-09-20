# Non-Primitive Data Types

The main non-primitive data type in JavaScript is **`Object`**. Objects can represent collections of related data and functionality.

```javascript
const user = {
  name: "Jane",
  age: 26,
  profession: "Web Developer",
};
```

---

## Object

An **object** is a collection of properties. Each property consists of a **key-value** pair.

### Accessing Object Properties

#### Dot Notation

```javascript
console.log(user.name);
```

Output:

```text
Jane
```

#### Bracket Notation

```javascript
console.log(user["name"]);
```

Output:

```text
Jane
```

---

### Objects Can Contain Functions

A function stored inside an object is commonly called a **method**.

```javascript
const user = {
  name: "Jane",

  greet() {
    console.log("Hello!");
  },
};

user.greet();
```

Output:

```text
Hello!
```

So objects can contain:

```text
Object
  |
  ├── Data
  |    ├── name
  |    └── age
  |
  └── Behavior
       └── greet()
```

---

## Built-in Objects

JavaScript provides many built-in objects that developers can use without creating them from scratch. Some commonly used built-in objects include:

```text
Built-in Objects
      |
      ├── Object
      ├── Array
      ├── Date
      ├── Math
      ├── RegExp
      ├── Map
      ├── Set
      ├── Promise
      ├── JSON
      └── Error
```

---

## Array

An **Array** is used to store an ordered collection of values.

```javascript
const fruits = ["Apple", "Mango", "Banana"];
```

Access an item:

```javascript
console.log(fruits[0]);
```

Output:

```text
Apple
```

Arrays are objects in JavaScript.

```javascript
typeof [];
```

returns:

```text
"object"
```

## Date

The `Date` object can be used to work with dates and times.

```javascript
const today = new Date();

console.log(today);
```

The exact output depends on the current date and time.

## Math

`Math` provides mathematical constants and functions.

```javascript
console.log(Math.max(10, 20, 30));
```

Output:

```text
30
```

## RegExp

`RegExp` represents regular expressions. Regular expressions are used for pattern matching.

```javascript
const pattern = /hello/i;

console.log(pattern.test("Hello World"));
```

Output:

```text
true
```

## Map

`Map` stores key-value pairs.

```javascript
const users = new Map();

users.set("name", "Jane");

console.log(users.get("name"));
```

Output:

```text
Jane
```

## Set

`Set` stores unique values.

```javascript
const numbers = new Set([1, 2, 2, 3, 3]);

console.log(numbers);
```

The duplicate values are removed.

Conceptually:

```text
[1, 2, 2, 3, 3]
        ↓
   Set
        ↓
 [1, 2, 3]
```

## Promise

A `Promise` represents the eventual completion or failure of an asynchronous operation.

```javascript
const promise = new Promise((resolve, reject) => {
  resolve("Success!");
});
```

# Primitive Data Types

> **Primitive values** are the basic building blocks of JavaScript values. Primitive values are **immutable**. This means the value itself cannot be changed. JavaScript has **7 primitive data types**:

## 1. String

A **string** represents textual data. Strings can be written using:

- Single quotes `'...'`
- Double quotes `"..."`
- Backticks `` `...` ``

```javascript
const name1 = "Jane";
const name2 = "John";
const name3 = `Doe`;
```

Backticks are called **template literals** when used to create strings. They are especially useful when inserting variables into strings.

### Strings Can Contain Different Characters

```javascript
const message = "Hello, World!";
const number = "123";
const symbols = "!@#$%";
```

## 2. Number

The **number** type represents numeric values. JavaScript's `Number` type can represent:

- Integers
- Floating-point numbers
- Positive numbers
- Negative numbers
- Special numeric values

```javascript
const age = 26;
const price = 499.99;
const temperature = -5;
```

### Special Number Values

JavaScript also has some special numeric values.

#### `Infinity`

```javascript
console.log(10 / 0);
```

Output:

```text
Infinity
```

#### `-Infinity`

```javascript
console.log(-10 / 0);
```

Output:

```text
-Infinity
```

#### `NaN`

`NaN` means **Not-a-Number**.

```javascript
console.log("hello" / 2);
```

Output:

```text
NaN
```

## 3. Boolean

A **boolean** represents a logical value. There are only two boolean values **`true`** and **`false`**. Booleans are commonly used in:

- Conditions
- Comparisons
- Loops
- Authentication logic
- Form validation
- Application state

Example:

```javascript
const age = 26;

const isAdult = age >= 18;

console.log(isAdult);
```

Output:

```text
true
```

## 4. BigInt

**BigInt** is used to represent integers larger than the maximum safe integer that the `Number` type can reliably represent. A BigInt can be created by adding `n` to the end of an integer. The `n` indicates that the value is a BigInt.

```javascript
const bigNumber = 123456789012345678901234567890n;
```

We can also use the `BigInt()` function:

```javascript
const bigNumber = BigInt("123456789012345678901234567890");
```

## 5. Undefined

`undefined` represents a value that has **not been assigned**. The variable exists, but no value has been assigned to it.

Example:

```javascript
let name;

console.log(name);
```

### Function with No Return Value

A function that does not explicitly return a value returns `undefined`.

```javascript
function greet() {
  console.log("Hello!");
}

const result = greet();

console.log(result);
```

Output:

```text
Hello!
undefined
```

## 6. Null

`null` represents the intentional absence of a value.

```javascript
const user = null;
```

Initially, there is no selected user.

Later:

```javascript
selectedUser = {
  name: "Jane",
};
```

### A Historical Quirk

There is an unusual behavior in JavaScript:

```javascript
typeof null;
```

returns:

```text
"object"
```

This is a **long-standing historical behavior** in JavaScript. It does not mean that `null` is actually an object. `null` is a **primitive value**.

## 7. Symbol

A **Symbol** is a primitive data type used to create **unique identifiers**. Every Symbol is unique. A Symbol can be created using:

```javascript
const id = Symbol();
```

### Symbols with Descriptions

We can provide a description. The description is mainly useful for debugging.

```javascript
const id = Symbol("userId");
```

### Symbols as Object Properties

Symbols can be used as object property keys.

```javascript
const userId = Symbol("userId");

const user = {
  name: "Jane",
  [userId]: 101,
};

console.log(user[userId]);
```

Output:

```text
101
```

Symbols are particularly useful when we need a property key that should not accidentally conflict with ordinary string property names.

# Indexed Collections

**Indexed collections** are data structures where values are accessed using a numerical **index**. JavaScript provides two main indexed collections - **Array** and **Typed Array**.

```text
Indexed Collections
        |
   ┌────┴────┐
   |         |
 Array   Typed Array
```

---

## Arrays

An **Array** is an ordered collection of values. Each value has a numerical index starting from `0`.

```javascript
const fruits = ["Apple", "Banana", "Mango"];
```

The indexes are:

```text
 Array
┌───────┬────────┬────────┐
│ Apple │ Banana │ Mango  │
└───────┴────────┴────────┘
    0        1        2
```

### Accessing Elements

```javascript
console.log(fruits[0]);
// Apple

console.log(fruits[2]);
// Mango
```

The first element is always at index `0`.

### Creating Arrays

Using an array literal is the most common approach:

```javascript
const numbers = [10, 20, 30, 40];
```

We can also create an empty array then add values:

```javascript
const users = [];

users.push("John");
users.push("Jane");
```

### Arrays Can Contain Different Types

JavaScript arrays are not restricted to one data type.

```javascript
const data = ["Jane", 26, true, null, { role: "developer" }];
```

Although this is allowed, in real applications arrays are usually kept logically consistent.

### Array Length

The `length` property tells us how many elements an array contains.

```javascript
const fruits = ["Apple", "Banana", "Mango"];

console.log(fruits.length);
// 3
```

### Common Array Methods

Arrays provide many methods for working with collections.

| Method       | Purpose                              |
| ------------ | ------------------------------------ |
| `push()`     | Add to the end                       |
| `pop()`      | Remove from the end                  |
| `unshift()`  | Add to the beginning                 |
| `shift()`    | Remove from the beginning            |
| `slice()`    | Create a portion of an array         |
| `splice()`   | Add/remove elements                  |
| `includes()` | Check whether a value exists         |
| `indexOf()`  | Find an element's index              |
| `find()`     | Find the first matching element      |
| `filter()`   | Create an array of matching elements |
| `map()`      | Transform every element              |
| `forEach()`  | Run a function for each element      |
| `reduce()`   | Reduce values into one result        |

### Arrays Are Objects

Arrays are technically a special kind of **object**.

```javascript
const numbers = [10, 20, 30];

console.log(typeof numbers);
// "object"
```

However, arrays are specifically designed for **ordered collections**.

---

## Typed Arrays

> **Typed arrays** are array-like objects designed to work with **raw binary data**. Unlike normal arrays, a typed array has a specific numeric data type. A typed array instead stores values using a specific binary numeric representation.

Typed arrays are especially useful when working with things such as **binary files, graphics, audio, video, Web APIs, and performance-sensitive numeric data**.

| Typed Array    | Data Type                    |
| -------------- | ---------------------------- |
| `Int8Array`    | 8-bit signed integer         |
| `Uint8Array`   | 8-bit unsigned integer       |
| `Int16Array`   | 16-bit signed integer        |
| `Uint16Array`  | 16-bit unsigned integer      |
| `Int32Array`   | 32-bit signed integer        |
| `Uint32Array`  | 32-bit unsigned integer      |
| `Float32Array` | 32-bit floating-point number |
| `Float64Array` | 64-bit floating-point number |

Example:

```javascript
const numbers = new Int32Array([10, 20, 30, 40]);

console.log(numbers);
// Int32Array(4) [10, 20, 30, 40]
```

Here every value is stored as a **32-bit signed integer**.

### Creating a Typed Array

```javascript
const numbers = new Int32Array(4);

console.log(numbers);
// Int32Array(4) [0, 0, 0, 0]
```

The argument `4` creates space for four values.

We can also initialize it with values:

```javascript
const numbers = new Int32Array([10, 20, 30]);

console.log(numbers);
// Int32Array(3) [10, 20, 30]
```

### Accessing Typed Array Elements

Typed arrays use indexes just like normal arrays.

```javascript
const numbers = new Int32Array([10, 20, 30]);

console.log(numbers[0]);
// 10

console.log(numbers[2]);
// 30
```

---

## Array vs Typed Array

| Feature          | Array                     | Typed Array                                        |
| ---------------- | ------------------------- | -------------------------------------------------- |
| Stores           | Any JavaScript values     | Specific numeric type                              |
| Type flexibility | High                      | Fixed                                              |
| Size             | Flexible                  | Fixed length                                       |
| Designed for     | General collections       | Binary/numeric data                                |
| Common use       | Lists of application data | Binary data, graphics, files, low-level operations |

# Data Types

A **data type** defines the kind of value that a variable can hold and describes how that value can be used.

Example:

```javascript
const name = "Jane"; // String
const age = 26; // Number
const isDeveloper = true; //  Boolean
```

JavaScript has two broad categories of data types:

```text
                         JavaScript Data Types
                                  |
                  ┌───────────────┴───────────────┐
                  |                               |
              Primitive                     Non-Primitive
                  |                               |
        ┌─────────┼─────────┐              ┌──────┴──────┐
        |         |         |              |             |
      String    Number    Boolean        Object     Built-in Objects
        |         |         |
      BigInt   Undefined   Null
      Symbol
```

---

## `typeof` Operator

The `typeof` operator is used to determine the type of a value.

Syntax:

```javascript
typeof value;
```

Example:

```javascript
const name = "Jane";

console.log(typeof name);
```

Output:

```text
string
```

### `typeof` Examples

```javascript
typeof "Hello"; // "string"

typeof 42; // "number"

typeof true; // "boolean"

typeof 123n; // "bigint"

typeof undefined; // "undefined"

typeof Symbol(); // "symbol"

typeof {}; // "object"

typeof []; // "object"

typeof function () {}; // "function"

typeof null; // "object"
```

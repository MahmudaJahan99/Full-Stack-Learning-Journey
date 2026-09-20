# Variables

> A **variable** is a named container used to store a value in a JavaScript program. Variables allow us to store information and use that information later.

Example:

```js
let name = "Jane";
let age = 26;

console.log(name);
console.log(age);
```

Output:

```text
Jane
26
```

- `name` and `age` is a variable.
- `"Jane"` is the value stored in `name`.
- `26` is the value stored in `age`.

---

## Variable Declarations

JavaScript provides three keywords for declaring variables **`var`**, **`let`**, and **`const`**. Although all three can be used to create variables, they behave differently.

### `var`

`var` is the older way of declaring variables in JavaScript.

The value can be changed:

```javascript
var age = 26;

age = 27;

console.log(age);
```

Output:

```text
27
```

A `var` variable can also be **redeclared** within the same scope:

```javascript
var name = "Jane";

var name = "John";

console.log(name);
```

Output:

```text
John
```

This behavior is one of the reasons modern JavaScript generally prefers `let` and `const` over `var`.

### `let`

`let` was introduced with **ES6 (ECMAScript 2015)**. It is used when the value of a variable may need to change.

```javascript
let age = 26;

age = 27;

console.log(age);
```

Output:

```text
27
```

Unlike `var`, a `let` variable **cannot be redeclared in the same scope**.

```javascript
let name = "Jane";

let name = "John";
```

This produces an error.

However, the value can be reassigned:

```javascript
let name = "Jane";

name = "John";

console.log(name);
```

Output:

```text
John
```

### `const`

`const` is used when a variable should **not be reassigned** after initialization.

```javascript
const country = "Bangladesh";
```

Trying to reassign it produces an error.

```javascript
const country = "Bangladesh";

country = "Oman";
```

A `const` variable **must be initialized when it is declared**.

```javascript
const name = "Jane";
```

This is invalid:

```javascript
const name;
```

---

## `var` vs `let` vs `const`

| Feature                         |    `var`    | `let` | `const` |
| ------------------------------- | :---------: | :---: | :-----: |
| Can be declared                 |     ✅      |  ✅   |   ✅    |
| Can be reassigned               |     ✅      |  ✅   |   ❌    |
| Can be redeclared in same scope |     ✅      |  ❌   |   ❌    |
| Function scoped                 |     ✅      |  ❌   |   ❌    |
| Block scoped                    |     ❌      |  ✅   |   ✅    |
| Hoisted                         |     ✅      |  ✅   |   ✅    |
| Accessible before declaration   | `undefined` |  ❌   |   ❌    |

> **Important:** `let` and `const` are hoisted, but they cannot be accessed before their declaration because of the **Temporal Dead Zone (TDZ)**.

---

# Mental Model

```text
                         VARIABLES
                             |
              ┌──────────────┼──────────────┐
              |              |              |
          Declaration       Scope         Naming
              |              |              |
       ┌──────┼──────┐   ┌───┼────┬────┐    |
       |      |      |   |   |    |    |    |
      var    let    const Global Function Block
                                      |
                                   Hoisting
                                      |
                             ┌────────┴────────┐
                             |                 |
                            var           let / const
                             |                 |
                         undefined            TDZ
```

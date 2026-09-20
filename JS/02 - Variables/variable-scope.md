# Variable Scopes

> **Scope** determines where a variable can be accessed in a program. Scope answers the question: "Where can I use this variable?" JavaScript has several important types of scope:

1. Global Scope
2. Function Scope
3. Block Scope

---

## 1. Global Scope

A variable declared outside functions and blocks is generally in the **global scope**.

```javascript
const name = "Jane";

function greet() {
  console.log(name);
}

greet();
```

Output:

```text
Jane
```

The function can access `name` because `name` was declared in an outer/global scope.

### Global Variables

Example:

```javascript
const language = "JavaScript";

console.log(language);

function showLanguage() {
  console.log(language);
}

showLanguage();
```

Both places can access `language`.

However, having many global variables can make a program harder to maintain because many parts of the application can access and modify shared state.

---

## 2. Function Scope

A variable declared inside a function using `var`, `let`, or `const` is local to that function.

```javascript
function greet() {
  const message = "Hello!";

  console.log(message);
}

greet();
```

This works.

But:

```javascript
function greet() {
  const message = "Hello!";
}

console.log(message);
```

This produces an error because `message` only exists inside the function.

> `var` is **function scoped**.

---

## 3. Block Scope

A **block** is code surrounded by curly braces `{}`.

Example:

```javascript
{
  // This is a block
}
```

Blocks can appear in:

- `if` statements
- `for` loops
- `while` loops
- standalone blocks
- other control structures

`let` and `const` are **block scoped**.

```javascript
{
  let name = "Jane";
  const age = 26;

  console.log(name);
  console.log(age);
}
```

They can be accessed inside the block. But not outside:

```javascript
{
  let name = "Jane";
}

console.log(name);
```

This produces an error.

---

## `var` vs Block Scope

`var` does **not** have block scope.

```javascript
if (true) {
  var message = "Hello";
}

console.log(message);
```

Output:

```text
Hello
```

The `if` block did not create a separate scope for the `var` variable.

---

## Scope Example

Consider this code:

```javascript
const globalName = "Jane";

function greet() {
  const functionMessage = "Hello";

  if (true) {
    const blockMessage = "Welcome";

    console.log(globalName);
    console.log(functionMessage);
    console.log(blockMessage);
  }
}

greet();
```

The scopes can be visualized as:

```text
Global Scope
│
├── globalName
│
└── Function Scope
    │
    ├── functionMessage
    │
    └── Block Scope
        │
        └── blockMessage
```

# Hoisting

**Hoisting** is the behavior where JavaScript processes certain declarations before executing the code. This can make it appear as though declarations have been moved to the top of their scope. However, JavaScript does **not literally move your source code**.

It is better to think of hoisting as part of how JavaScript's execution process handles declarations.

## Hoisting with `var`

Consider:

```javascript
console.log(name);

var name = "John";
```

Output: `undefined`

Conceptually, the declaration is available before the assignment:

```javascript
var name;

console.log(name);

name = "John";
```

The variable exists, but its value is initially `undefined`.

## Hoisting with `let` and `const`

`let` and `const` are also hoisted in the sense that their declarations are processed when the scope is created. However, they cannot be accessed before their declaration.

```javascript
console.log(name);

let name = "Jane";
```

This produces a **`ReferenceError`**.

The same happens with `const`:

```javascript
console.log(name);

const name = "Jane";
```

Again **`ReferenceError`**

---

## Temporal Dead Zone

The period between entering a scope and reaching the declaration of a `let` or `const` variable is called the **Temporal Dead Zone (TDZ)**.

Example:

```javascript
console.log(name); // ReferenceError

let name = "Jane";
```

Conceptually:

```text
Scope begins
     |
     ↓
Temporal Dead Zone
     |
     ↓
let name = "Jane";
     |
     ↓
Variable can now be accessed
```

The same applies to `const`.

```javascript
console.log(country); // ReferenceError

const country = "Bangladesh";
```

---

## Hoisting Comparison

```javascript
// var
console.log(a); // undefined

var a = 10;
```

```javascript
// let
console.log(b); // ReferenceError

let b = 20;
```

```javascript
// const
console.log(c); // ReferenceError

const c = 30;
```

A simplified comparison:

| Declaration | Hoisted | Accessible before declaration |
| ----------- | :-----: | :---------------------------: |
| `var`       |   ✅    |      Yes, as `undefined`      |
| `let`       |   ✅    |              ❌               |
| `const`     |   ✅    |              ❌               |

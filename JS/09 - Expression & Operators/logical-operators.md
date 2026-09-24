# Logical Operators

**Logical operators** work with boolean logic and are also commonly used to control which values are evaluated or returned.

The main logical operators are:

- `&&` — AND
- `||` — OR
- `!` — NOT
- `??` — Nullish coalescing

## Logical AND `&&`

Both sides need to be truthy for the result to be truthy. With boolean values:

```javascript
true && true; // true

true && false; // false

false && true; // false

false && false; // false
```

## `&&` Returns Values

JavaScript's `&&` operator does not necessarily return `true` or `false`. It returns one of its operands.

```javascript
console.log("Hello" && "World");
// World

console.log(0 && "Hello");
// 0
```

JavaScript evaluates from left to right and stops as soon as the result is known. This behavior is called **short-circuit evaluation**.

## Logical OR `||`

With booleans:

```javascript
true || false;
// true

false || false;
// false
```

For values:

```javascript
console.log("" || "Guest");
// Guest
```

Because an empty string is falsy.

## Logical NOT `!`

`!` reverses the truthiness of a value.

```javascript
!true;
// false

!false;
// true

!0;
// true

!"hello";
// false
```

Double NOT can be used to convert a value to a boolean:

```javascript
!!"Hello";
// true

!!0;
// false
```

## Nullish Coalescing `??`

The `??` operator returns the right-hand value only when the left-hand value is either **`null`** or **`undefined`**

```javascript
const username = null;

console.log(username ?? "Guest");
// Guest
```

Compare it with `||`:

```javascript
const count = 0;

console.log(count || 10);
// 10

console.log(count ?? 10);
// 0
```

The difference is:

```text
||  → checks truthiness

??  → checks only null / undefined
```

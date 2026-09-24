# Unary Operators

A **unary operator** operates on **one operand**.

```text
operator + operand
       ↓
     result
```

Examples include:

- `++`
- `--`
- `+`
- `-`
- `!`
- `typeof`
- `void`
- `delete`

## Unary Plus `+`

Unary `+` attempts to convert its operand to a number.

```javascript
console.log(+"10");
// 10

console.log(typeof +"10");
// "number"
```

The result is a number.

## Unary Minus `-`

Unary `-` converts a value to a number and negates it.

```javascript
console.log(-"10");
// -10
```

## Increment `++`

The `++` operator increases a numeric value by `1`.

```javascript
let count = 5;

count++;

console.log(count);
// 6
```

### Prefix

```javascript
let count = 5;

console.log(++count);
// 6
```

The value is increased **before** it is returned.

### Postfix

```javascript
let count = 5;

console.log(count++);
// 5

console.log(count);
// 6
```

The original value is returned first, then the variable is increased.

## Decrement `--`

The `--` operator decreases a value by `1`.

```javascript
let count = 5;

count--;

console.log(count);
// 4
```

It also has prefix and postfix forms:

```javascript
--count;
count--;
```

## Logical NOT `!`

The `!` operator converts a value to a boolean and reverses it.

```javascript
console.log(!true);
// false

console.log(!false);
// true
```

It also works with truthy and falsy values:

```javascript
console.log(!0);
// true

console.log(!"hello");
// false
```

## `typeof`

The `typeof` operator returns a string describing the type of a value.

```javascript
console.log(typeof "Hello");
// "string"

console.log(typeof 42);
// "number"

console.log(typeof true);
// "boolean"
```

## `delete`

The `delete` operator removes a property from an object.

```javascript
const user = {
  name: "Jane",
  age: 26,
};

delete user.age;

console.log(user);
// { name: "Jane" }
```

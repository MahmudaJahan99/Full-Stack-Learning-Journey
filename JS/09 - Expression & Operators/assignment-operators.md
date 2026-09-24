# Assignment Operators

**Assignment operators** assign values to variables. The basic assignment operator is **`=`**

```javascript
let age = 26;
```

Here `26` is assigned to `age`.

## Compound Assignment Operators

JavaScript provides shorthand forms for performing an operation and assigning the result.

| Operator | Equivalent to      |
| -------- | ------------------ |
| `=`      | `x = value`        |
| `+=`     | `x = x + value`    |
| `-=`     | `x = x - value`    |
| `*=`     | `x = x * value`    |
| `/=`     | `x = x / value`    |
| `%=`     | `x = x % value`    |
| `**=`    | `x = x ** value`   |
| `<<=`    | `x = x << value`   |
| `>>=`    | `x = x >> value`   |
| `>>>=`   | `x = x >>> value`  |
| `&=`     | `x = x & value`    |
| `=`      | `x = x \| value`   |
| `^=`     | `x = x ^ value`    |
| `&&=`    | `x = x && value`   |
| `=`      | `x = x \|\| value` |
| `??=`    | `x = x ?? value`   |

## Logical Assignment

JavaScript also provides logical assignment operators.

### `&&=`

Assigns the right-hand value only when the left-hand value is truthy.

```javascript
let isLoggedIn = true;

isLoggedIn &&= false;

console.log(isLoggedIn);
// false
```

### `||=`

Assigns the right-hand value when the left-hand value is falsy.

```javascript
let username = "";

username ||= "Guest";

console.log(username);
// Guest
```

### `??=`

Assigns the right-hand value only when the left-hand value is `null` or `undefined`.

```javascript
let name;

name ??= "Unknown";

console.log(name);
// Unknown
```

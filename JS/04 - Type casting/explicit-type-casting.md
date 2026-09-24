# Explicit Type Casting

> **Explicit type casting** means that you intentionally convert a value to another type. JavaScript provides several functions for this.

The most commonly used are:

```text
Number()
String()
Boolean()
```

---

## Convert to String

Syntax:

```javascript
String(value);
```

Example:

```javascript
String(100);
// "100"

String(true);
// "true"

String(false);
// "false"

String(null);
// "null"

String(undefined);
// "undefined"
```

---

## Template Literals

Another common way to create strings from values is using template literals.

```javascript
const age = 26;

const message = `I am ${age} years old.`;
```

Here, JavaScript converts the value inserted into the template literal into its string representation.

Output:

```text
I am 26 years old.
```

---

## Convert to Number

Syntax:

```javascript
Number(value);
```

Example:

```javascript
Number("100");
// 100

Number("10.5");
// 10.5

Number(true);
// 1

Number(false);
// 0

Number(null);
// 0

Number("");
// 0

Number("hello");
// NaN
```

---

## `parseInt()`

It parses an integer from a string.

```javascript
parseInt();
```

It can behave differently from `Number()`.

```javascript
Number("42px");
// NaN

parseInt("42px", 10);
// 42
```

`parseInt()` stops reading when it encounters a character that isn't part of the integer.

---

## `parseFloat()`

`parseFloat()` is used to parse a floating-point number.

```javascript
parseFloat("10.5");
// 10.5

parseFloat("10.5px");
// 10.5
```

---

## Convert to Boolean

Syntax:

```javascript
Boolean(value);
```

Truthy values example:

```javascript
Boolean("hello");
// true

Boolean(100);
// true

Boolean(-1);
// true

Boolean([]);
// true

Boolean({});
// true
```

Falsy values example:

```javascript
Boolean("");
// false

Boolean(0);
// false

Boolean(false);
// false

Boolean(null);
// false

Boolean(undefined);
// false

Boolean(NaN);
// false
```

### The Double NOT `!!`

This is a common shorthand for converting a value to a boolean.

Example:

```javascript
const value = "hello";

console.log(!!value);
// true
```

Conceptually:

```text
"hello"
   ↓
! "hello"
   ↓
false
   ↓
! false
   ↓
true
```

# Type Casting

**Type casting** refers to changing a value from one data type to another. JavaScript frequently needs to work with values of different types.

String → Number example:

```javascript
const value = "100";

const number = Number(value);
```

Number → String example:

```javascript
const value = 100;

const text = String(value);
```

JavaScript supports conversion between several types. Common conversions include:

```text
String  ↔  Number
String  ↔  Boolean
Number  ↔  Boolean
```

```text
                    Type Casting
                         |
              ┌──────────┴──────────┐
              |                     |
          Explicit               Implicit
          Conversion             Conversion
              |                     |
        Programmer tells       JavaScript
        JS to convert          converts automatically
```

Type casting becomes especially important when working with:

- User input
- Forms
- APIs
- URL parameters
- Local storage
- JSON
- Databases
- Mathematical calculations

---

# Type Conversion vs Type Coercion

## Type Conversion

**Type conversion** usually means that the programmer intentionally changes a value's type.
This is also called **explicit conversion** or **explicit type casting**.

```javascript
const age = "26";

const numberAge = Number(age);
```

## Type Coercion

**Type coercion** happens when JavaScript **automatically converts a value from one type to another** while evaluating an expression.

```javascript
const age = "26";

console.log(age + 1);
```

Output `261`. Because the `+` operator sees a string and converts the number `1` into a string. The conversion happened **automatically**.

---

## Common Conversion Methods

| Conversion | Method         | Example               | Result  |
| ---------- | -------------- | --------------------- | ------- |
| To String  | `String()`     | `String(123)`         | `"123"` |
| To Number  | `Number()`     | `Number("123")`       | `123`   |
| To Boolean | `Boolean()`    | `Boolean(1)`          | `true`  |
| To Integer | `parseInt()`   | `parseInt("123", 10)` | `123`   |
| To Float   | `parseFloat()` | `parseFloat("12.5")`  | `12.5`  |

---

## Important Edge Cases

Type conversion can sometimes produce surprising results.

### Empty String to Number

```javascript
Number("");
// 0
```

```javascript
Boolean("");
// false
```

---

### `null` Conversion

```javascript
Number(null);
// 0
```

```javascript
String(null);
// "null"
```

```javascript
Boolean(null);
// false
```

The same value can therefore produce different results depending on the target type.

---

### `undefined` Conversion

```javascript
Number(undefined);
// NaN
```

```javascript
String(undefined);
// "undefined"
```

```javascript
Boolean(undefined);
// false
```

---

### String + Number

This is one of the most common type-coercion examples:

```javascript
console.log("5" + 2);
```

Result:

```text
52
```

BecaSyntax:

```text
"5" + 2
 ↓
"5" + "2"
 ↓
"52"
```

---

### String (arithmetic operation) Number

```javascript
console.log("10" + 5); // 105
console.log("10" - 5); // 5
console.log("10" * 5); // 50
console.log("10" / 5); // 2
```

---

```text
                         TYPE CASTING
                              |
               ┌──────────────┴──────────────┐
               |                             |
          Type Conversion                Type Coercion
               |                             |
          ┌────┴────┐                  ┌─────┴─────┐
          |         |                  |           |
       Explicit   Manual            Implicit    Automatic
          |         |                  |
          ↓         ↓                  ↓
       Number()  String()          "10" + 5
       Boolean() parseInt()       "10" - 5
       String()  parseFloat()     if ("hello")
```

# String Operators

JavaScript uses the `+` operator for both **numeric addition** and **string concatenation**.

## String Concatenation

When one or both operands are strings, `+` can concatenate them.

```javascript
const firstName = "Jane";
const lastName = "Doe";

const fullName = firstName + " " + lastName;

console.log(fullName);
// Jane Doe
```

The strings are joined together.

### `+=` with Strings

The `+=` assignment operator can also concatenate strings.

```javascript
let message = "Hello";

message += " Jane";

console.log(message);
// Hello Jane
```

## `+` and Type Coercion

The `+` operator behaves differently depending on the values.

```javascript
10 + 5;
// 15
```

But:

```javascript
"10" + 5;
// "105"
```

Because the number is converted to a string and concatenated.

This is one reason the `+` operator is special in JavaScript.

## Other Operators with Strings

Operators such as `-`, `*`, and `/` generally attempt numeric conversion.

```javascript id="string006"
"10" - 5;
// 5

"10" * 2;
// 20

"10" / 2;
// 5
```

---

## Operator Precedence

When an expression contains multiple operators, JavaScript follows **operator precedence** to determine the order of evaluation.

Example

```javascript
const result = 10 + 5 * 2;

console.log(result);
// 20
```

Multiplication happens before addition.

Parentheses can be used to make the intended order explicit. A good practice is to use parentheses when they make complex expressions easier to understand.

```javascript
const result = (10 + 5) * 2;

console.log(result);
// 30
```

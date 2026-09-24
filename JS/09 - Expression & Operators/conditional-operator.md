# Conditional Operator

The **conditional operator**, also called the **ternary operator**, provides a short way to choose between two expressions. It uses:

```text
condition ? expressionIfTrue : expressionIfFalse
```

Example:

```javascript
const age = 20;

const status = age >= 18 ? "Adult" : "Minor";

console.log(status);
// Adult
```

It is essentially a compact form of:

```javascript id="cond003"
let status;

if (age >= 18) {
  status = "Adult";
} else {
  status = "Minor";
}
```

The conditional operator is useful for **simple decisions that produce a value**.

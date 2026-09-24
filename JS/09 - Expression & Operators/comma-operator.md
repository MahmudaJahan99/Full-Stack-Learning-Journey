# Comma Operator

The **comma operator** evaluates multiple expressions from left to right and returns the value of the **last expression**.

Syntax:

```javascript
(expression1, expression2, expression3);
```

Example:

```javascript
const result = (1 + 2, 3 + 4);

console.log(result);
// 7
```

The expressions are evaluated in order:

```text
1 + 2 → 3
   ↓
3 + 4 → 7
   ↓
result → 7
```

The earlier result (`3`) is discarded.

## Comma Operator in a `for` Loop

The comma operator can be useful when a `for` loop needs multiple expressions.

```javascript
for (let i = 0, j = 5; i < 5; i++, j--) {
  console.log(i, j);
}
```

Here the comma separates multiple expressions in the initialization and update sections. The comma used to separate function arguments is not necessarily the comma operator.

Example

```javascript
console.log("Hello", "World");
```

The comma here separates function arguments.

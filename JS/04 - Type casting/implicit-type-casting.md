# Implicit Type Casting

**Implicit type casting** occurs when JavaScript automatically converts a value to another type. Programmers do not directly call a conversion function.

Example:

```javascript
console.log("Hello " + 123);
```

Output `Hello 123`. The number is implicitly converted to a string.

## The `+` Operator

The `+` operator can perform two different operations:

### Addition

```javascript
10 + 5;
```

Result `15`

### String concatenation

```javascript
"10" + 5;
```

Result `"105"`

Therefore, the type of the operands matters.

---

## Numeric Conversion

JavaScript can also implicitly convert values into numbers in certain situations.

### Subtraction

```javascript
console.log("10" - 5);
```

Output `5`. JavaScript converts `"10"` into `10`.

### Multiplication

```javascript
console.log("10" * 2);
```

Output `20`. The string `"10"` is converted into a number.

### Division

```javascript
console.log("20" / 5);
```

Output `4`. The string `"20"` is converted into a number.

---

## Boolean Conversion

JavaScript can also convert values to booleans. This behavior is called **truthy/falsy coercion**.

Example:

```javascript
if ("hello") {
  console.log("This runs!");
}
```

The string `"hello"` is treated as **truthy**, so the condition passes.

Similarly:

```javascript
if (0) {
  console.log("This runs!");
}
```

Nothing is printed because `0` is **falsy**.

### Truthy and Falsy Values

When JavaScript expects a boolean, values can be automatically interpreted as either `true` or `false`. Common falsy values are:

```text
false
0
-0
0n
""
null
undefined
NaN
```

Everything else is generally **truthy**.

Example:

```text
"hello"  → true
"0"      → true
[]       → true
{}       → true
42       → true
-10      → true
```

Notice:

```javascript
Boolean("0");
```

returns **`true`** because `"0"` is a **non-empty string**.

---

## Implicit Conversion with Equality

JavaScript has two equality operators **`==`** and **`===`**. They behave differently.

### Loose Equality `==`

`==` allows type coercion.

```javascript
console.log(5 == "5");
```

Output `true`

JavaScript converts the string `"5"` to a number before comparing.

### Strict Equality `===`

`===` does **not** perform this type coercion.

```javascript
console.log(5 === "5");
```

Output `false`

```text
5       → Number
"5"     → String
```

The types are different.

# Equality Comparisons

**Equality comparisons** are used to determine whether two JavaScript values should be considered equal. JavaScript provides several ways to compare values:

```text
                    EQUALITY COMPARISONS
                            |
              ┌─────────────┴─────────────┐
              |                           |
     Value Comparison Operators    Equality Algorithms
              |                           |
       ┌──────┼──────┐          ┌────────┼──────────────┐
       |      |      |          |        |              |
      ==     ===   Object.is()  IsLoosely IsStrictly  SameValue
                                Equal     Equal       SameValueZero
```

The important thing to understand is that **different comparison methods follow different rules**.

---

# Value Comparison Operators

JavaScript provides three important ways to directly compare values:

- `==` — Loose equality
- `===` — Strict equality
- `Object.is()` — Same-value comparison

---

## Loose Equality `==`

The **loose equality operator** compares two values after allowing **type coercion** when necessary.

```javascript
console.log(10 == "10");
// true

console.log(true == 1);
// true

console.log(false == 0);
// true
```

The values have different types, but `==` allows JavaScript to convert one value before comparing them.

### `null` and `undefined`

One important special case:

```javascript
console.log(null == undefined);
// true

console.log(null == 0);
// false

console.log(undefined == 0);
// false
```

So `null` and `undefined` are loosely equal to each other, but not to `0`.

---

## Strict Equality `===`

The **strict equality operator** compares values **without performing type coercion**.

```javascript
console.log(5 === "5");
// false

console.log(10 === "10");
// false

console.log(true === 1);
// false

console.log(false === 0);
// false
```

The types must match before the values can be considered equal.

```javascript
console.log("hello" === "hello");
// true

console.log(100 === 100);
// true

console.log(true === true);
// true
```

Same type and same value gives true.

---

## Object.is()

`Object.is()` compares two values using the **SameValue** algorithm.

```javascript
console.log(Object.is(5, 5));
// true

console.log(Object.is(5, "5"));
// false
```

At first glance, `Object.is()` looks very similar to `===`. However, there are two important differences involving:

- `NaN`
- `+0` and `-0`

### `NaN`

With strict equality:

```javascript
console.log(NaN === NaN);
// false

console.log(Object.is(NaN, NaN));
// true
```

This is one of the key differences between `===` and `Object.is()`.

### `+0` and `-0`

JavaScript has both positive zero and negative zero.

```javascript
console.log(+0 === -0);
// true

console.log(Object.is(+0, -0));
// false
```

So `Object.is()` distinguishes between `+0` and `-0`.

---

# Equality Algorithms

The operators above are built around different **equality algorithms** defined by the JavaScript specification. The important algorithms are:

- **IsLooselyEqual**
- **IsStrictlyEqual**
- **SameValue**
- **SameValueZero**

These algorithms describe **how JavaScript decides whether two values are equal**.

## IsLooselyEqual

The **IsLooselyEqual** algorithm is the conceptual algorithm behind the `==` operator. Its major characteristic is **It may perform type conversion before comparing values.**

```javascript
a == b;
```

uses loose equality rules.

However, loose equality has many special cases.

```javascript
"" == 0;
// true

"0" == false;
// true
```

This is one reason developers often prefer `===` when they want predictable type-sensitive comparisons.

---

## IsStrictlyEqual

The **IsStrictlyEqual** algorithm is the conceptual algorithm behind the `===` operator.

```javascript
a === b;
```

It does **not** perform type coercion.

However, strict equality has many special cases.

```javascript
NaN === NaN;
// false
```

`NaN` is not strictly equal to itself. This is because the strict equality algorithm treats `NaN` as unequal to `NaN`.

```javascript
+0 === -0;
// true
```

Strict equality considers them equal.

---

## SameValue

The **SameValue** algorithm is used by `Object.is()`.

```javascript
Object.is(a, b);
```

The key differences from strict equality are:

```text
              SameValue
                  |
        ┌─────────┴─────────┐
        |                   |
     NaN = NaN          +0 ≠ -0
        |                   |
       true                true
```

Examples:

```javascript
Object.is(NaN, NaN);
// true

Object.is(+0, -0);
// false
```

For most ordinary values, `Object.is()` behaves like `===`.

```javascript
Object.is(10, 10);
// true

Object.is("hello", "hello");
// true

Object.is(true, true);
// true
```

---

## SameValueZero

**SameValueZero** is very similar to **SameValue**, but it treats `+0` and `-0` as equal.

```javascript
+0 === -0;
// true

Object.is(+0, -0);
// false
```

SameValueZero is particularly important when working with certain JavaScript collections and methods. For example, `Set` uses SameValueZero semantics when determining whether a value is already present.

```javascript
const values = new Set();

values.add(NaN);
values.add(NaN);

console.log(values.size);
// 1
```

Even though:

```javascript
NaN === NaN;
// false
```

the `Set` recognizes the two `NaN` values as the same.

Similarly:

```javascript
const values = new Set([+0, -0]);

console.log(values.size);
// 1
```

`+0` and `-0` are treated as the same value.

---

## Operator → Algorithm

You can connect the operators to their underlying comparison rules like this:

```text
==
│
└── IsLooselyEqual


===
│
└── IsStrictlyEqual


Object.is()
│
└── SameValue
```

`SameValueZero` does not have a dedicated comparison operator. Instead, it is used internally by certain JavaScript operations and collections.

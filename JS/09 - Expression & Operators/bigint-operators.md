# BigInt Operators

**BigInt** is a JavaScript primitive used to represent integers larger than the safe range of the `Number` type. A BigInt can be created by adding `n` to an integer:

```javascript id="bigint001"
const bigNumber = 12345678901234567890n;
```

## Arithmetic with BigInt

BigInts support many arithmetic operators:

```javascript
const a = 10n;
const b = 3n;

console.log(a + b);
// 13n

console.log(a - b);
// 7n

console.log(a * b);
// 30n

console.log(a / b);
// 3n

console.log(a % b);
// 1n

console.log(a ** 2n);
// 100n
```

## BigInt Cannot Be Mixed Directly with Number

This is not allowed:

```javascript id="bigint004"
10n + 5;
```

JavaScript throws a `TypeError`.

We need to use the same numeric type:

```javascript id="bigint005"
10n + 5n;
// 15n
```

or explicitly convert:

```javascript id="bigint006"
Number(10n) + 5;
// 15
```

Be careful when converting very large BigInts to `Number`, because precision can be lost.

## BigInt Comparisons

BigInt values can be compared with other BigInts:

```javascript
10n > 5n;
// true
```

They can also be compared with Numbers using relational operators:

```javascript
10n > 5;
// true
```

Equality has its own distinction:

```javascript
10n === 10;
// false

10n == 10;
// true
```

The strict comparison checks the types, while loose equality may perform conversion.

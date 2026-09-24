# Bitwise Operators

**Bitwise operators** work with the binary representation of numbers. JavaScript represents ordinary numbers internally as **32-bit bitwise operands** when bitwise operations are performed. The main bitwise operators are:

| Operator | Name                         |
| -------- | ---------------------------- |
| `&`      | AND                          |
| `\|`     | OR                           |
| `^`      | XOR                          |
| `~`      | NOT                          |
| `<<`     | Left shift                   |
| `>>`     | Sign-propagating right shift |
| `>>>`    | Zero-fill right shift        |

## Bitwise AND `&`

The AND operation produces `1` only when **both bits are `1`**.

```javascript
console.log(5 & 3);
// 1
```

## Bitwise OR `|`

OR produces `1` when **at least one bit is `1`**.

```javascript
5 | 3;
// 7
```

## Bitwise XOR `^`

XOR produces `1` when the two bits are **different**.

```javascript
5 ^ 3;
// 6
```

## Bitwise NOT `~`

The `~` operator flips every bit.

```javascript
~5;
// -6
```

Bitwise NOT can be surprising because JavaScript's bitwise operations work with signed 32-bit integers.

## Bitwise Shift Operators

### Left Shift `<<`

Moves bits to the left.

```javascript
5 << 1;
// 10
```

### Right Shift `>>`

Moves bits to the right while preserving the sign bit.

```javascript
10 >> 1;
// 5
```

### Zero-Fill Right Shift `>>>`

Moves bits to the right and fills the left side with zeros.

```javascript
10 >>> 1;
// 5
```

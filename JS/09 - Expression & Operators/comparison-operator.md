# Comparison Operators

**Comparison operators** compare values and normally produce a boolean result:

## Equality Operators

```javascript id="comp001"
5 == "5";
// true

5 === "5";
// false

5 != "5";
// false

5 !== "5";
// true
```

- `==` → loose equality
- `===` → strict equality
- `!=` → loose inequality
- `!==` → strict inequality

## Relational Operators

### Greater Than `>`

```javascript id="comp002"
10 > 5;
// true
```

### Less Than `<`

```javascript id="comp003"
10 < 5;
// false
```

### Greater Than or Equal `>=`

```javascript id="comp004"
10 >= 10;
// true
```

### Less Than or Equal `<=`

```javascript id="comp005"
5 <= 10;
// true
```

---

# Comparison Summary

| Operator | Meaning               |
| -------- | --------------------- |
| `==`     | Loose equality        |
| `!=`     | Loose inequality      |
| `===`    | Strict equality       |
| `!==`    | Strict inequality     |
| `>`      | Greater than          |
| `<`      | Less than             |
| `>=`     | Greater than or equal |
| `<=`     | Less than or equal    |

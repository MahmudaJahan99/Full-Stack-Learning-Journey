# Expressions & Operators

> **Expressions** and **operators** are fundamental parts of JavaScript. An **expression** is a piece of code that produces a value. An **operator** is a symbol or keyword that performs an operation on one or more values.

---

## Expressions

An expression is anything that JavaScript can evaluate to produce a value.

Examples:

```javascript
5;
// 5

5 + 10;
// 15

age >= 18;
// true

"Hello " + "World";
// "Hello World"
```

A useful mental model:

```text
Expression
    |
    ↓
JavaScript evaluates it
    |
    ↓
Produces a value
```

---

## Operators

Operators tell JavaScript **what operation to perform**.

```javascript
10 + 5;
```

Here:

```text
10     +     5
↑      ↑     ↑
value operator value
```

The `+` operator tells JavaScript to add the values.

JavaScript has many categories of operators:

```text
                      OPERATORS
                          |
      ┌──────────┬────────┼────────┬───────────┐
      |          |        |        |           |
  Arithmetic Comparison Logical Assignment   Unary
      |
      ├── Bitwise
      ├── Conditional
      ├── Comma
      ├── BigInt
      └── String
```

---

| Category        | Main operators                                 | Purpose                         |
| --------------- | ---------------------------------------------- | ------------------------------- |
| **Conditional** | `? :`                                          | Choose between two expressions  |
| **Comma**       | `,`                                            | Evaluate multiple expressions   |
| **Unary**       | `+`, `-`, `!`, `++`, `--`, `typeof`, `delete`  | Operate on one operand          |
| **Assignment**  | `=`, `+=`, `-=`, `*=`, etc.                    | Assign/update values            |
| **Comparison**  | `==`, `===`, `!=`, `!==`, `>`, `<`, `>=`, `<=` | Compare values                  |
| **Arithmetic**  | `+`, `-`, `*`, `/`, `%`, `**`                  | Perform mathematical operations |
| **Bitwise**     | `&`, `\|`, `^`, `~`, `<<`, `>>`, `>>>`         | Work with binary bits           |
| **Logical**     | `&&`, `\|\|`, `!`, `??`                        | Combine/check logical values    |
| **BigInt**      | `+`, `-`, `*`, `/`, `%`, `**`, etc.            | Operate on BigInt values        |
| **String**      | `+`, `+=`                                      | Concatenate strings             |

# Loops and Iterations

**Loops** allow JavaScript to repeatedly execute a block of code while a condition is true or while there are still values to process.

Without a loop, we might have to write:

```javascript
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
```

With a loop:

```javascript
for (let i = 0; i < 5; i++) {
  console.log("Hello");
}
```

The loop handles the repetition for us. JavaScript provides several loop structures:

```text
                    LOOPS & ITERATIONS
                           |
        ┌──────────────────┼──────────────────┐
        |                  |                  |
     for loop         while loops       for...of / for...in
                         |
                   ┌─────┴─────┐
                   |           |
                 while      do...while
                   |
             break / continue
```

---

## `for` Loop

> The **`for` loop** is useful when we know the general structure of the repetition, especially when we have a counter.

Syntax:

```javascript
for (initialization; condition; update) {
  // code to repeat
}
```

A `for` loop has three main parts **`initialization;`**, **`condition;`**, and **`update`**,

For:

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

the process is:

```text
1. initialization
       ↓
   let i = 0
       ↓
2. condition
   i < 5 ?
       ↓
     true
       ↓
3. execute body
   console.log(i)
       ↓
4. update
   i++
       ↓
5. condition again
       ↓
   repeat...
       ↓
   i < 5 → false
       ↓
      stop
```

### Initialization

The initialization runs once before the loop starts. It usually creates and initializes a counter.

### Condition

The condition determines whether the loop should continue. If it is `true`, the loop body executes. If it is `false`, the loop stops.

### Update

The update runs after each iteration. It changes the counter so the loop can eventually stop.

---

## `while` Loop

A **`while` loop** repeatedly executes code **while a condition is true**.

Syntax:

```javascript
while (condition) {
  // code
}
```

Example:

```javascript
let count = 0;

while (count < 5) {
  console.log(count);
  count++;
}
```

Output:

```text
0
1
2
3
4
```

### How `while` Works

The condition is checked **before every iteration**.

```text
          condition
              ↓
        ┌─────┴─────┐
        |           |
      true        false
        |           |
        ↓           ↓
    run body       stop
        |
        ↓
   check again
```

This means a `while` loop can execute **zero times**.

Example:

```javascript
let count = 10;

while (count < 5) {
  console.log(count);
}
```

Nothing is printed because the condition is already `false`.

### Infinite Loops

A loop must eventually be able to make its condition false.

```javascript
let count = 0;

while (count < 5) {
  console.log(count);
}
```

This loop would continue forever because `count` never changes. This is called an **infinite loop**.

---

## `do...while` Loop

A `do...while` loop is similar to a `while` loop, but the body executes **before the condition is checked**.

Syntax:

```javascript
do {
  // code
} while (condition);
```

Example:

```javascript
let count = 0;

do {
  console.log(count);
  count++;
} while (count < 5);
```

Output:

```text
0
1
2
3
4
```

```text
       run body
          ↓
    check condition
          ↓
     ┌────┴────┐
     |         |
   true      false
     |         |
     ↓         ↓
 run again    stop
```

The important difference is **when the condition is checked**.

---

## `break`

The **`break` statement** immediately terminates the loop.

Example:

```javascript
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break;
  }

  console.log(i);
}
```

Output:

```text
0
1
2
3
4
```

When `i` becomes `5`:

```text
i === 5
   ↓
 break
   ↓
loop stops
```

The remaining iterations are skipped.

### `break` with `while`

```javascript
let count = 0;

while (count < 10) {
  if (count === 5) {
    break;
  }

  console.log(count);
  count++;
}
```

The loop stops when `count` reaches `5`.

---

## `continue`

The **`continue` statement** skips the current iteration and moves to the next one.

Example:

```javascript
for (let i = 0; i < 5; i++) {
  if (i === 2) {
    continue;
  }

  console.log(i);
}
```

Output:

```text
0
1
3
4
```

When `i` is `2`, the rest of that iteration is skipped.

```text
i = 0 → run
i = 1 → run
i = 2 → continue → skip
i = 3 → run
i = 4 → run
```

---

## `for...of` Loop

The **`for...of` loop** is used to iterate over the **values of an iterable**. It is commonly used with:

- Arrays
- Strings
- Sets
- Maps
- Typed arrays
- Other iterable objects

Syntax:

```javascript
for (const value of iterable) {
  // code
}
```

### `for...of` with an Array

```javascript
const fruits = ["Apple", "Banana", "Mango"];

for (const fruit of fruits) {
  console.log(fruit);
}
```

Output:

```text
Apple
Banana
Mango
```

We get the **values**, not the indexes.

```text
Array:
┌─────────┬─────────┬────────┐
│  Apple  │ Banana  │ Mango  │
└─────────┴─────────┴────────┘
     ↑         ↑         ↑
   value     value     value

for...of → gives these values
```

### `for...of` with a String

Strings are iterable too.

```javascript
const word = "Hello";

for (const character of word) {
  console.log(character);
}
```

Output:

```text
H
e
l
l
o
```

### `for...of` with a Set

```javascript
const numbers = new Set([10, 20, 30]);

for (const number of numbers) {
  console.log(number);
}
```

Output:

```text
10
20
30
```

### `for...of` with a Map

A `Map` produces key-value pairs when iterated with `for...of`.

```javascript
const user = new Map([
  ["name", "Jane"],
  ["age", 26],
]);

for (const [key, value] of user) {
  console.log(key, value);
}
```

Output:

```text
name Jane
age 26
```

---

## `for...in` Loop

The **`for...in` loop** iterates over the **enumerable property keys** of an object.

Syntax:

```javascript
for (const key in object) {
  // code
}
```

Example:

```javascript
const user = {
  name: "Jane",
  age: 26,
  role: "Developer",
};

for (const key in user) {
  console.log(key);
}
```

Output:

```text
name
age
role
```

The variable `key` contains the property name.

### Getting Values with `for...in`

We can use the key to access the corresponding value:

```javascript
const user = {
  name: "Jane",
  age: 26,
  role: "Developer",
};

for (const key in user) {
  console.log(key, user[key]);
}
```

Output:

```text
name Jane
age 26
role Developer
```

---

### `for...in` with Arrays

Technically, `for...in` can be used with arrays:

```javascript
const fruits = ["Apple", "Banana", "Mango"];

for (const index in fruits) {
  console.log(index);
}
```

Output:

```text
0
1
2
```

It gives us the **indexes**, not the values.

To get the value:

```javascript
for (const index in fruits) {
  console.log(fruits[index]);
}
```

---

## Loop Comparison Table

| Loop         | Iterates over             | Common use                             |
| ------------ | ------------------------- | -------------------------------------- |
| `for`        | Controlled repetition     | Counters / indexes                     |
| `while`      | Condition                 | Unknown number of iterations           |
| `do...while` | Condition after execution | Must execute at least once             |
| `for...of`   | Values                    | Arrays, strings, Sets, Maps, iterables |
| `for...in`   | Property keys             | Objects                                |

---

## Nested Loops

A loop can exist inside another loop.

Example:

```javascript
for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 2; j++) {
    console.log(i, j);
  }
}
```

The inner loop completes its iterations for each iteration of the outer loop.

Conceptually:

```text
Outer loop
   |
   ├── Inner loop
   │      ├── iteration 1
   │      └── iteration 2
   |
   ├── Inner loop
   │      ├── iteration 1
   │      └── iteration 2
   |
   └── Inner loop
          ├── iteration 1
          └── iteration 2
```

Nested loops are useful for working with things such as grids, tables, and nested collections.

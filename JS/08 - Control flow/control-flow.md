# Control Flow

> **Control flow** describes the order in which JavaScript executes statements and decides **which parts of the code should run**. Normally, JavaScript executes code from top to bottom. Control flow statements allow us to change this normal flow.

---

# Conditional Statements

**Conditional statements** allow JavaScript to execute different code depending on whether a condition is true or false.

## `if` statement

The `if` statement executes a block of code if a condition is `true`.

Basic syntax:

```javascript
if (condition) {
  // code
}
```

Example:

```javascript
const age = 20;

if (age >= 18) {
  console.log("Adult");
}
```

The condition _`age >= 18`_ is evaluated first. Because it is `true`, the code inside the `if` block runs.

## `if...else` statement

Use `else` when we want to provide an alternative when the condition is false.

```javascript
const age = 16;

if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}

// Minor
```

The flow is:

```text
             condition
                 |
          ┌──────┴──────┐
          |             |
        true          false
          |             |
          ↓             ↓
      if block      else block
          |             |
          └──────┬──────┘
                 ↓
              continue
```

## `else if` statement

When there are multiple conditions, we can use `else if`.

```javascript
const score = 75;

if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else if (score >= 70) {
  console.log("C");
} else {
  console.log("Needs improvement");
}

// C
```

JavaScript checks the conditions from **top to bottom**. Once one condition is true, its block executes and the remaining conditions are skipped.

## Nested `if` Statements

An `if` statement can exist inside another `if` statement. Nested conditions are useful when one decision depends on another.

```javascript
const age = 25;
const hasTicket = true;

if (age >= 18) {
  if (hasTicket) {
    console.log("You can enter.");
  }
}
```

Conceptually:

```text
if age >= 18
    |
   Yes
    |
    ↓
if hasTicket
    |
   Yes
    |
    ↓
Run code
```

---

## Multiple Conditions

Conditions can use logical operators.

### AND `&&`

Both conditions must be true.

```javascript
const age = 25;
const hasTicket = true;

if (age >= 18 && hasTicket) {
  console.log("You can enter.");
}
```

### OR `||`

At least one condition must be true.

```javascript
const isWeekend = true;
const isHoliday = false;

if (isWeekend || isHoliday) {
  console.log("Day off");
}
```

### NOT `!`

Reverses a boolean value.

```javascript
const isLoggedIn = false;

if (!isLoggedIn) {
  console.log("Please log in.");
}
```

---

## `switch`

A **`switch` statement** is useful when we want to compare one expression against several possible values.

Syntax:

```javascript
switch (expression) {
  case value1:
    // code
    break;

  case value2:
    // code
    break;

  default:
  // code
}
```

Example:

```javascript
const day = "Monday";

switch (day) {
  case "Monday":
    console.log("Start of the week");
    break;

  case "Friday":
    console.log("Almost weekend");
    break;

  case "Sunday":
    console.log("Weekend");
    break;

  default:
    console.log("Regular day");
}

// Start of the week
```

The expression is evaluated once. JavaScript then checks it against each `case`.

```text
                 expression
                     |
                     ↓
               ┌───────────┐
               │   switch  │
               └─────┬─────┘
                     |
       ┌─────────────┼─────────────┐
       ↓             ↓             ↓
    case A         case B        case C
       |             |             |
      no            yes           no
                     |
                     ↓
                  run code
```

### `break`

The `break` statement stops the `switch` after a matching case has executed.

```javascript
const number = 2;

switch (number) {
  case 1:
    console.log("One");
    break;

  case 2:
    console.log("Two");
    break;

  case 3:
    console.log("Three");
    break;
}

// Two
```

Without `break`, JavaScript can continue executing the following cases. This behavior is called **fall-through**.

### Fall-Through

Consider:

```javascript
const number = 1;

switch (number) {
  case 1:
    console.log("One");

  case 2:
    console.log("Two");

  case 3:
    console.log("Three");
}
```

Output:

```text
One
Two
Three
```

Once `case 1` matches, execution continues into the following cases because there is no `break`.

This can sometimes be intentional.

---

### `default`

The `default` case runs when none of the cases match.

```javascript
const fruit = "Orange";

switch (fruit) {
  case "Apple":
    console.log("Apple");
    break;

  case "Banana":
    console.log("Banana");
    break;

  default:
    console.log("Unknown fruit");
}

// Unknown fruit
```

`default` is similar to the final `else` in an `if...else if...else` structure.

### `switch` Uses Strict Comparison

`switch` case matching uses **strict equality (`===`)** semantics.

For example:

```javascript
const value = 5;

switch (value) {
  case "5":
    console.log("String");
    break;

  case 5:
    console.log("Number");
    break;
}

// Number
```

`5` and `"5"` are different types.

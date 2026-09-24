# Exceptional Handling

> Not every problem in a program is a normal conditional decision. Sometimes an operation **fails or encounters an exceptional situation**. JavaScript provides exception handling mechanisms for these situations:

## `throw` Statement

The **`throw` statement** is used to explicitly generate an exception.

Syntax:

```javascript
throw value;
```

Example:

```javascript
throw new Error("Something went wrong");
```

When JavaScript encounters `throw`, normal execution of the current flow stops and the exception moves up until something handles it.

Example:

```javascript
const age = 15;

if (age < 18) {
  throw new Error("You must be 18 or older.");
}

console.log("Access granted.");
```

Because the condition is true, the error is thrown. The following statement does not execute:

```javascript
console.log("Access granted.");
```

### Throwing Different Values

JavaScript technically allows many values to be thrown:

```javascript
throw "Something went wrong";
```

or:

```javascript
throw 404;
```

or:

```javascript
throw { message: "Something went wrong" };
```

However, it is generally better to throw an **Error object**:

```javascript
throw new Error("Something went wrong");
```

This provides useful error information such as the error message and stack trace.

---

## `try...catch`

The `try...catch` statement allows us to **attempt an operation and handle an exception if one occurs**.

Syntax:

```javascript
try {
  // code that may throw
} catch (error) {
  // handle the error
}
```

Example:

```javascript
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.log(error.message);
}

// Something went wrong
```

If no exception occurs, the `catch` block is skipped. If an exception occurs, JavaScript jumps to the `catch` block.

```text
              try block
                  |
             Run code
                  |
          ┌───────┴───────┐
          |               |
      No error          Error
          |               |
          ↓               ↓
      continue        catch block
                          |
                          ↓
                       handle
```

### Catching an Error

The `catch` block receives the thrown error:

```javascript
try {
  throw new Error("Invalid operation");
} catch (error) {
  console.log(error);
}
```

We can inspect its properties:

```javascript
try {
  throw new Error("Invalid operation");
} catch (error) {
  console.log(error.name);
  console.log(error.message);
}
```

Output:

```text
Error
Invalid operation
```

---

## `finally`

The `finally` block contains code that executes **after the `try`/`catch` process**, regardless of whether an exception occurred.

Syntax:

```javascript
try {
  // code
} catch (error) {
  // handle error
} finally {
  // always run this
}
```

Example:

```javascript
try {
  console.log("Trying...");
} catch (error) {
  console.log("Error occurred");
} finally {
  console.log("Finished");
}
```

Output:

```text
Trying...
Finished
```

### With an Error

```javascript
try {
  throw new Error("Something went wrong");
} catch (error) {
  console.log(error.message);
} finally {
  console.log("Cleanup complete");
}
```

Output:

```text
Something went wrong
Cleanup complete
```

The `finally` block runs even though an error occurred. `finally` is useful for **cleanup operations** that should happen regardless of success or failure.

Conceptually:

```text
             TRY
              |
        ┌─────┴─────┐
        |           |
      success      error
        |           |
        |         CATCH
        |           |
        └─────┬─────┘
              |
           FINALLY
              |
         cleanup code
```

---

## `try`, `catch`, and `finally` Together

```javascript
try {
  const result = riskyOperation();

  console.log(result);
} catch (error) {
  console.log("Something went wrong:");
  console.log(error.message);
} finally {
  console.log("Operation finished.");
}
```

The general flow is:

```text
try
 ↓
Did an exception occur?
 ├── No  → continue
 │
 └── Yes → catch
             ↓
         handle error
             |
             ↓
          finally
             |
             ↓
          continue
```

---

## Error Objects

JavaScript provides **Error objects** to represent errors that occur during program execution. The basic error object is:

```javascript
new Error("Something went wrong");
```

Example:

```javascript
const error = new Error("Invalid input");

console.log(error.name);
console.log(error.message);
```

Output:

```text
Error
Invalid input
```

---

## Important Error Properties

An Error object commonly provides:

### `name`

Describes the type/name of the error.

```javascript
const error = new Error("Something went wrong");

console.log(error.name);
// Error
```

### `message`

Contains the description of the error.

```javascript
console.log(error.message);
// Something went wrong
```

### `stack`

Contains information about where the error was created and the call path that led to it. The exact stack output depends on the JavaScript environment.

```javascript
console.log(error.stack);
```

---

## Common Built-in Error Types

JavaScript provides several built-in error types.

```text
Error
├── TypeError
├── ReferenceError
├── SyntaxError
├── RangeError
├── URIError
├── EvalError
└── AggregateError
```

1. `Error` - The general-purpose error type:
2. `TypeError` - Occurs when an operation is performed on a value of an inappropriate type.
3. `ReferenceError` - Occurs when code tries to access a variable that does not exist.
4. `SyntaxError` - Occurs when JavaScript code has invalid syntax.
5. `RangeError` - Occurs when a value is outside an allowed range.

---

## Checking the Error Type

Because different Error objects have different constructors, you can use `instanceof` to check the type.

```javascript
try {
  // some operation
} catch (error) {
  if (error instanceof TypeError) {
    console.log("A type error occurred.");
  }
}
```

For a general error:

```javascript
if (error instanceof Error) {
  console.log("An error occurred.");
}
```

## Throwing a Specific Error

Instead of always throwing a generic `Error`, you can use a more specific type.

```javascript
function setAge(age) {
  if (typeof age !== "number") {
    throw new TypeError("Age must be a number.");
  }

  return age;
}
```

Then:

```javascript
try {
  setAge("twenty");
} catch (error) {
  console.log(error.name);
  console.log(error.message);
}
```

Output:

```text
TypeError
Age must be a number.
```

---

## Conditional Flow vs Exception Flow

These two concepts should not be confused.

### Conditional statement

You **expect** a condition and choose what to do.

```javascript
if (age >= 18) {
  console.log("Allowed");
} else {
  console.log("Not allowed");
}
```

### Exception handling

Something has gone wrong or an exceptional situation needs to be reported.

```javascript
try {
  processData();
} catch (error) {
  console.log("Could not process data.");
}
```

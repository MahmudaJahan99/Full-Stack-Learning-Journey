# CSS Functions

> CSS functions are **special built-in expressions that perform an operation or generate a value**. CSS functions allow us to create values that are more **dynamic, flexible, and reusable**.

Syntax:

```css
property: function-name(argument);
```

Example:

```css
width: calc(100% - 40px);
```

Some functions can accept multiple arguments:

```css
width: min(90%, 1200px);
```

Some functions can even be nested:

```css
font-size: clamp(1rem, calc(0.5rem + 2vw), 2rem);
```

Without functions, many CSS values have to be fixed. A function can make the value flexible:

```text
CSS Functions
      │
      ├── Calculate values
      │      └── calc()
      │
      ├── Choose a value
      │      ├── min()
      │      └── max()
      │
      ├── Control a range
      │      └── clamp()
      │
      ├── Generate colors
      │      ├── rgb()
      │      ├── hsl()
      │      └── ...
      │
      └── Generate other CSS values
```

## `calc()`

The `calc()` function performs calculations.

Syntax:

```css
calc(expression)
```

Example:

```css
.box {
  width: calc(100% - 40px);
}
```

This means:

```text
100% - 40px
```

The browser calculates the final value.

### `calc()` Operators

`calc()` supports:

- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division

---

## `min()`

The `min()` function returns the **smallest value** from the values provided.

Syntax:

```css
min(value1, value2, ...)
```

Example:

```css
.container {
  width: min(90%, 1200px);
}
```

This means container width can use 90% of available width but cannot exceed 1200px. The browser chooses whichever value is smaller.

---

## `max()`

The `max()` function returns the **largest value** from the values provided.

Syntax:

```css
max(value1, value2, ...)
```

Example:

```css
.box {
  width: max(300px, 50%);
}
```

The browser chooses whichever value is larger. This can be useful when an element needs to maintain a minimum size.

---

## `clamp()`

The `clamp()` function is especially useful for **responsive sizing**. It allows to define `minimum`, `preferred`, and `maximum`.

Syntax:

```css
clamp(minimum, preferred, maximum)
```

Example:

```css
h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

This means:

```text
Minimum  → 2rem
Preferred → 5vw
Maximum  → 4rem
```

The browser chooses a value that stays within that range.

---

# `calc()`, `min()`, `max()`, and `clamp()`

These functions are closely related.

| Function  | Purpose                                  |
| --------- | ---------------------------------------- |
| `calc()`  | Calculate a value                        |
| `min()`   | Choose the smallest value                |
| `max()`   | Choose the largest value                 |
| `clamp()` | Keep a value between minimum and maximum |

---

## Color Functions

CSS also provides functions for defining colors.

### `rgb()`

`rgb()` represents a color using `Red`, `Green`, and `Blue`.

```css
color: rgb(255, 0, 0);
```

### `rgba()`

`rgba()` adds an **alpha channel**, which controls transparency.

```css
background-color: rgba(0, 0, 0, 0.5);
```

### `hsl()`

`hsl()` represents a color using `Hue`, `Saturation`, and `Lightness`.

```css
color: hsl(240, 100%, 50%);
```

### `hsla()`

`hsla()` adds transparency.

```css
background-color: hsla(240, 100%, 50%, 0.5);
```

---

## Gradient Functions

CSS gradients are also created using functions.

### `linear-gradient()`

Creates a gradient along a straight line.

```css
.hero {
  background: linear-gradient(to right, blue, purple);
}
```

Visual idea:

```text
Blue ───────────────────→ Purple
```

### `radial-gradient()`

Creates a gradient spreading outward from a central point.

```css
.hero {
  background: radial-gradient(circle, white, blue);
}
```

Visual idea:

```text
        White
      ↗   ↑   ↖
    /     ●     \
   ───────┼───────
          ↓
         Blue
```

---

## Transform Functions

The `transform` property uses functions to transform elements.

Example:

```css
.box {
  transform: translateX(50px);
}
```

Common transform functions include:

```text
translate() → Moves an element
translateX() → Moves an element horozontally
translateY() → Moves an element vertically

rotate() → Rotates an element

scale() → Changes the size of an element
scaleX() → Changes the size of an element horozontally
scaleY() → Changes the size of an element vertically

skew() → Moves an element
skewX() → Moves an element horozontally
skewY() → Moves an element vertically
```

---

## Other Useful CSS Functions

CSS contains many other functions beyond the core ones above. Some useful examples include:

| Function        | Purpose                                                       |
| --------------- | ------------------------------------------------------------- |
| `var()`         | Uses a CSS custom property                                    |
| `url()`         | References a resource such as an image                        |
| `attr()`        | Reads an HTML attribute value                                 |
| `env()`         | Accesses environment variables provided by the browser/device |
| `repeat()`      | Repeats values in CSS Grid                                    |
| `minmax()`      | Defines a minimum and maximum size in Grid                    |
| `fit-content()` | Creates a size that fits available content/space              |
| `counter()`     | Generates counter values                                      |
| `counters()`    | Generates nested counter values                               |

---

### Functions Can Be Nested

CSS functions can be placed inside other CSS functions.

Example:

```css
font-size: clamp(1rem, calc(0.5rem + 2vw), 2rem);
```

Here:

```text
clamp()
  │
  └── calc()
```

The browser evaluates the nested calculation as part of determining the final value.

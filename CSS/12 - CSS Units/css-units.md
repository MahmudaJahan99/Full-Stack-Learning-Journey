# CSS Units

CSS units are used to define the **size, spacing, dimensions, and positioning** of elements. CSS units can be broadly divided into:

```text
                    CSS Units
                        │
            ┌───────────┴───────────┐
            │                       │
      Absolute Units          Relative Units
            │                       │
        px, pts, ...       %, em, rem, vw, vh, ...
                                    │
                            Units with Functions
                              calc(), min(),
                              max(), clamp()
```

---

## Absolute vs Relative Units

The main difference is **what the unit's size is based on**.

**Absolute units** - Their size is generally fixed and does not depend on another element or the viewport.
**Relative units** - Their size is calculated **relative to something else**, such as:

- Parent element
- Root element
- Font size
- Viewport

### Absolute Units

Absolute units represent a fixed physical or screen-based measurement. The most commonly used absolute unit in everyday CSS is **`px`**. Other absolute units include:

- cm
- mm
- Q
- in
- pc
- pt
- px

### Relative Units

Relative units depend on another value. Common CSS relative units include:

```text
%       → relative to another dimension/context
em      → relative to the element's font size
rem     → relative to the root element's font size
vw      → relative to viewport width
vh      → relative to viewport height
vmin    → relative to smaller viewport dimension
vmax    → relative to larger viewport dimension
```

---

| Unit   | Type     | Relative to                         |
| ------ | -------- | ----------------------------------- |
| `px`   | Absolute | CSS pixel                           |
| `%`    | Relative | Relevant containing/reference value |
| `em`   | Relative | Font-size context                   |
| `rem`  | Relative | Root font size                      |
| `vw`   | Relative | Viewport width                      |
| `vh`   | Relative | Viewport height                     |
| `vmin` | Relative | Smaller viewport dimension          |
| `vmax` | Relative | Larger viewport dimension           |

---

## Units with Functions

CSS also provides functions that allows to **calculate or choose values dynamically**. These are extremely useful for responsive layouts.

Important functions include:

```text
calc()
min()
max()
clamp()
```

### `calc()`

`calc()` allows CSS to perform calculations.

Example:

```css
.container {
  width: calc(100% - 40px);
}
```

This means the element can remain responsive while maintaining a fixed amount of space.

```text
100% - 40px
```

One of the biggest advantages of `calc()` is that we can combine different units.

```css
.container {
  width: calc(100% - 40px);
}
```

Here:

```text
100% → relative
40px → absolute
```

### `min()`

The `min()` function returns the **smaller** of the provided values.

Syntax:

```css
property: min(value1, value2);
```

Example:

```css
.container {
  width: min(90%, 1200px);
}
```

This means to use whichever is smaller: `90%` or `1200px`. So the container can be responsive but will not become wider than `1200px`.

### `max()`

The `max()` function returns the **larger** of the provided values.

Syntax:

```css
property: max(value1, value2);
```

Example:

```css
.container {
  width: max(300px, 50%);
}
```

This means to use whichever is larger: `300px` or `50%`. So it can help ensure that an element does not become smaller than a desired value.

### `clamp()`

`clamp()` is particularly useful for **responsive typography**. This allows a value to have:

1. A minimum
2. A preferred value
3. A maximum

Syntax:

```css
property: clamp(minimum, preferred, maximum);
```

Example:

```css
h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

This means:

```text
Minimum    → 2rem
Preferred  → 5vw
Maximum    → 4rem
```

The browser adjusts the value based on the viewport while respecting the minimum and maximum limits.

---

| Function  | Purpose                                   |
| --------- | ----------------------------------------- |
| `calc()`  | Performs a calculation                    |
| `min()`   | Chooses the smallest value                |
| `max()`   | Chooses the largest value                 |
| `clamp()` | Keeps a value between minimum and maximum |

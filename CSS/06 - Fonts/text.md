# CSS — Text Styling

CSS provides several properties for controlling the **appearance, alignment, spacing, and visual effects of text**.

---

## Color

The `color` property sets the **color of text**.

Syntax

```css
selector {
  color: value;
}
```

Example

```css
p {
  color: blue;
}
```

### Different Ways to Specify Colors

#### Color Name

```css
h1 {
  color: red;
}
```

#### HEX

```css
h1 {
  color: #ff0000;
}
```

#### RGB

```css
h1 {
  color: rgb(255, 0, 0);
}
```

#### HSL

```css
h1 {
  color: hsl(0, 100%, 50%);
}
```

---

## Direction

The `direction` property specifies the **direction in which text flows**.

Syntax

```css
selector {
  direction: value;
}
```

The two main values are:

```css
direction: ltr;
direction: rtl;
```

### LTR — Left to Right

```css
p {
  direction: ltr;
}
```

Text flows from **left to right**.

```text
Hello World
→ → → → →
```

This is commonly used for languages such as English.

### RTL — Right to Left

```css
p {
  direction: rtl;
}
```

Text flows from **right to left**.

```text
← ← ← ← ←
النص العربي
```

This is commonly used for languages such as Arabic and Hebrew.

---

## Text Alignment

The `text-align` property controls the **horizontal alignment of text** inside an element.

Syntax

```css
selector {
  text-align: value;
}
```

Common values include:

```css
text-align: left; /* text starts from the left */
text-align: right; /* text starts from the right */
text-align: center; /* text is centered */
text-align: justify; /* text is adjusted so that the lines generally reach both sides of the available width */
```

| Value     | Result                                  |
| --------- | --------------------------------------- |
| `left`    | Aligns text to the left                 |
| `right`   | Aligns text to the right                |
| `center`  | Centers text                            |
| `justify` | Spreads text across the available width |

---

## Text Decoration

The `text-decoration` property adds or removes **decorative lines** from text.

Syntax

```css
selector {
  text-decoration: value;
}
```

Common values include:

```css
text-decoration: none; /* removes the default underline from links */
text-decoration: underline; /* text is underlined */
text-decoration: overline; /* text has a line above it */
text-decoration: line-through; /* text has a line through it */
```

---

## Text Transform

The `text-transform` property controls the **capitalization of text**.

Syntax

```css
selector {
  text-transform: value;
}
```

Common values include:

```css
text-transform: uppercase;
text-transform: lowercase;
text-transform: capitalize;
text-transform: none;
```

| Value        | Result                    |
| ------------ | ------------------------- |
| `uppercase`  | ALL CAPITAL LETTERS       |
| `lowercase`  | all lowercase letters     |
| `capitalize` | First Letter Of Each Word |
| `none`       | Original text             |

---

## Text Spacing

CSS provides properties for controlling the **space between characters and words**.

### Letter Spacing

The `letter-spacing` property controls the space between **individual characters**.

Example:

```css
h1 {
  letter-spacing: 3px;
}
```

```text
Normal:
HELLO

More spacing:
H E L L O
```

A negative value can also reduce the spacing:

```css
h1 {
  letter-spacing: -1px;
}
```

### Word Spacing

The `word-spacing` property controls the space between **words**.

Example

```css
p {
  word-spacing: 10px;
}
```

```text
Normal:
Hello World

More spacing:
Hello          World
```

---

## Line Height

The `line-height` property controls the **vertical space between lines of text**.

Syntax

```css
selector {
  line-height: value;
}
```

Example:

```css
p {
  line-height: 1.6;
}
```

Appropriate line spacing gives the lines more vertical space and can make long paragraphs **much easier to read**.

### Using a Number

```css
p {
  line-height: 1.5;
}
```

The number acts as a multiplier of the element's font size.

For example, with:

```css
p {
  font-size: 16px;
  line-height: 1.5;
}
```

The approximate line height is:

```text
16px × 1.5 = 24px
```

### Using a Length

We can also use a specific unit:

```css
p {
  line-height: 24px;
}
```

---

## Text Shadows

The `text-shadow` property adds a **shadow effect behind text**.

Syntax

```css
selector {
  text-shadow: horizontal vertical blur color;
}
```

Example:

```css
h1 {
  text-shadow: 2px 2px 4px gray;
}
```

The values represent:

```text
text-shadow: 2px 2px 4px gray;
             │    │    │    │
             │    │    │    └── color
             │    │    └─────── blur
             │    └──────────── vertical offset
             └───────────────── horizontal offset
```

### Horizontal Offset

The first value controls the shadow's horizontal position. The shadow moves to the right.

### Vertical Offset

The second value controls the vertical position. The shadow moves downward.

### Blur

The third value controls how blurred the shadow is. A larger blur value produces a softer shadow.

## Multiple Text Shadows

Multiple shadows can be separated by commas. This allows more complex text effects.

```css
h1 {
  text-shadow:
    2px 2px 3px gray,
    -2px -2px 3px lightgray;
}
```

---

> **Text styling properties control how text looks, flows, aligns, and is spaced on a webpage.**

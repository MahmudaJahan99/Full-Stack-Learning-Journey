# CSS Border & Outline

Both **border** and **outline** can create a visible line around an element. However, they are **not the same**.

```text
                 OUTLINE
        ┌───────────────────────┐
        │       MARGIN          │
        │   ┌───────────────┐   │
        │   │    BORDER     │   │
        │   │ ┌───────────┐ │   │
        │   │ │  CONTENT  │ │   │
        │   │ └───────────┘ │   │
        │   └───────────────┘   │
        └───────────────────────┘
```

The main difference:

> **Border is part of the box model.**
> **Outline is drawn outside the border and does not take up layout space.**

---

## Border

The `border` property adds a visible line around an element.

Syntax:

```css
selector {
  border: width style color;
}
```

Example:

```css
.box {
  border: 2px solid black;
}
```

### Border Width

`border-width` controls the thickness of the border.

```css
.box {
  border-width: 5px;
}
```

We can also specify different widths for each side:

```css
.box {
  border-top-width: 2px;
  border-right-width: 4px;
  border-bottom-width: 6px;
  border-left-width: 8px;
}
```

### Border Style

`border-style` determines what the border looks like.

```css
border-style: solid;
border-style: dashed;
border-style: dotted;
border-style: double;
border-style: groove;
border-style: ridge;
border-style: inset;
border-style: outset;
border-style: none;
```

### Border Color

`border-color` controls the color of the border.

```css
.box {
  border-color: red;
}
```

We can use any CSS color format:

### Border Shorthand

Instead of writing:

```css
.box {
  border-width: 2px;
  border-style: solid;
  border-color: black;
}
```

We can write:

```css
.box {
  border: 2px solid black;
}
```

### Border on Individual Sides

Each side can be styled independently.

```css
.box {
  border-top: 2px solid red;
  border-right: 2px solid blue;
  border-bottom: 2px solid green;
  border-left: 2px solid orange;
}
```

This produces different borders on each side.

### Border Radius

The `border-radius` property makes the corners of an element rounded.

Example:

```css
.box {
  border: 2px solid black;
  border-radius: 10px;
}
```

```text
   ╭────────────────────╮
   │                    │
   │        BOX         │
   │                    │
   ╰────────────────────╯
```

A larger value creates more rounded corners

**If the element is square, `border-radius: 50%` can create a circle.**

### Border and the Box Model

Border is one of the parts of the CSS Box Model. Therefore, with the default, the border contributes to the element's total size.

```text
┌─────────────────────────┐
│         BORDER          │
│   ┌─────────────────┐   │
│   │     PADDING     │   │
│   │   ┌─────────┐   │   │
│   │   │ CONTENT │   │   │
│   │   └─────────┘   │   │
│   └─────────────────┘   │
└─────────────────────────┘
```

---

## Outline

The `outline` property draws a line **around an element's border**.

Syntax:

```css
selector {
  outline: width style color;
}
```

Example:

```css
.box {
  outline: 2px solid red;
}
```

Conceptually:

```text
      ┌───────────────────────┐
      │       OUTLINE         │
      │  ┌─────────────────┐  │
      │  │     BORDER      │  │
      │  │    ┌───────┐    │  │
      │  │    │ BOX   │    │  │
      │  │    └───────┘    │  │
      │  └─────────────────┘  │
      └───────────────────────┘
```

The outline is outside the border.

### Outline Width

`outline-width` controls the thickness.

```css
.box {
  outline-width: 3px;
}
```

Common values include _thin_, _medium_, and _thick_

### Outline Style

`outline-style` determines the appearance.

```css
outline-style: solid;
outline-style: dashed;
outline-style: dotted;
outline-style: double;
```

### Outline Color

`outline-color` controls the outline's color.

```css
.box {
  outline-color: red;
}
```

Like borders, outline colors can use different CSS color formats:

```css
outline-color: red;
outline-color: #ff0000;
outline-color: rgb(255, 0, 0);
```

### Outline Shorthand

The shorthand follows the same basic pattern as border. Meaning:

```text
outline: width style color;
```

### Outline and Focus

One of the most important uses of `outline` is showing which interactive element currently has **keyboard focus**.

For example:

```css
button:focus {
  outline: 3px solid blue;
}
```

When the button receives focus, the outline makes it visually clear which element is active. This is especially important for **keyboard accessibility**.

Avoid removing focus indicators without providing another visible way to identify the focused element.

---

# Border vs Outline

| Feature                           | Border            | Outline                   |
| --------------------------------- | ----------------- | ------------------------- |
| Part of Box Model                 | Yes               | No                        |
| Takes up layout space             | Yes               | No                        |
| Between padding and margin        | Yes               | No                        |
| Drawn outside border              | No                | Yes                       |
| Can style individual sides        | Yes               | No                        |
| Supports `border-radius` behavior | Yes               | Different                 |
| Common use                        | Visual boundaries | Focus/attention indicator |

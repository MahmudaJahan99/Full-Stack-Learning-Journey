# CSS Box Shadow

The `box-shadow` property adds a **shadow effect around an element's box**. The shadow appears around the element based on the values provided. It is commonly used to create:

- Cards
- Buttons
- Panels
- Modals
- Floating elements
- Depth and elevation effects

## Basic Box Shadow

Syntax:

```css
selector {
  box-shadow: offset-x offset-y blur-radius color;
}
```

Example:

```css
.card {
  box-shadow: 5px 5px 10px gray;
}
```

The values mean:

```text
5px     → offset-x
5px     → offset-y
10px    → blur-radius
gray    → color
```

---

### Horizontal Offset — `offset-x`

The first value controls the **horizontal position** of the shadow.

**Positive value** - Moves the shadow to the **right**.
**Negative value** - Moves the shadow to the **left**.

### Vertical Offset — `offset-y`

The second value controls the **vertical position** of the shadow.

**Positive value** - Moves the shadow **down**.
**Negative value** - Moves the shadow **up**.

### Blur Radius

The third value controls how **soft or sharp** the shadow is.

**Small blur value** - creates a relatively sharp shadow.
**Larger blur value** - creates a more spread-out, softer-looking shadow.

### Shadow Color

The last value controls the shadow's color. We can use different CSS color formats.

### Spread Radius

There is another optional value called the **spread radius**. The spread radius controls how much the shadow **expands or contracts** before the blur is applied. The extended syntax is:

```css
box-shadow: offset-x offset-y blur-radius spread-radius color;
```

Example:

```css
.card {
  box-shadow: 5px 5px 10px 3px gray;
}
```

Here:

```text
5px  → horizontal offset
5px  → vertical offset
10px → blur
3px  → spread
gray → color
```

**Positive spread** - The shadow becomes **larger**.
**Negative spread** - The shadow becomes **smaller**.

---

## No Offset Shadow

We don't always need to move the shadow. In such cases, the shadow surrounds the element.

```css
.card {
  box-shadow: 0 0 10px gray;
}
```

Here:

```text
offset-x = 0
offset-y = 0
blur     = 10px
```

---

## `inset` Shadow

By default, the shadow appears **outside** the element. We can use `inset` to place the shadow **inside** the element.

```css
.card {
  box-shadow: inset 0 0 10px gray;
}
```

```text
┌─────────────────┐
│ ░░░░░░░░░░░░░░░ │
│ ░     CARD    ░ │
│ ░░░░░░░░░░░░░░░ │
└─────────────────┘
       ↑
   Inner shadow
```

`inset` changes the shadow from an **outer shadow** to an **inner shadow**.

---

## Multiple Box Shadows

We can apply multiple shadows to the same element. Separate each shadow with a comma.

```css
.card {
  box-shadow:
    0 4px 10px rgba(0, 0, 0, 0.2),
    0 8px 20px rgba(0, 0, 0, 0.1);
}
```

The browser layers the shadows together. This can create more complex visual effects.

---

## Box Shadow Does Not Take Up Layout Space

This is an important difference between `box-shadow` and the CSS box model. A shadow is **visual** and does not increase the element's layout dimensions.

Example:

```css
.card {
  width: 300px;
  height: 200px;
  box-shadow: 0 10px 20px gray;
}
```

The element's declared dimensions are still:

```text
Width  = 300px
Height = 200px
```

The shadow does not add extra width or height to the layout.

---

# Common Box Shadow Examples

### Subtle card

```css
.card {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
```

### Strong shadow

```css
.card {
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}
```

### Shadow around all sides

```css
.card {
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}
```

### Inner shadow

```css
.card {
  box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.2);
}
```

### Colored shadow

```css
.button {
  box-shadow: 0 5px 15px rgba(100, 50, 255, 0.3);
}
```

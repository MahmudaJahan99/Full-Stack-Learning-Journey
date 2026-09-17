# CSS — Fonts

Fonts control how **text looks and feels** on a webpage. CSS provides several properties for controlling typography, including:

- **Font families**
- **Font styles**
- **Font size**
- **Font weight**
- **Font shorthand**
- **Google Fonts**
- **Font variant**

---

## Font Families

The `font-family` property specifies **which font should be used** to display text.

Syntax:

```css
selector {
  font-family: font-name;
}
```

Example:

```css
body {
  font-family: Arial;
}
```

All text inside the `<body>` will use Arial, unless another rule overrides it.

### Font Stack

Sometimes a particular font may not be available on the user's device. We can provide multiple fonts as **fallbacks**.

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}
```

The browser tries the fonts from **left to right**. The last font is usually a **generic font family**.

```text
Arial
  ↓
Available?
  │
 ┌┴─────┐
Yes     No
 │       │
 ▼       ▼
Use    Helvetica
          ↓
       Available?
          │
       ┌──┴──┐
      Yes   No
       │     │
       ▼     ▼
      Use   sans-serif
```

### Common Generic Font Families

| Generic Family | Description                                |
| -------------- | ------------------------------------------ |
| `serif`        | Fonts with decorative strokes              |
| `sans-serif`   | Fonts without decorative strokes           |
| `monospace`    | Characters generally have equal width      |
| `cursive`      | Handwriting-style fonts                    |
| `fantasy`      | Decorative fonts                           |
| `system-ui`    | Uses the operating system's interface font |

---

## Font Styles

The `font-style` property controls whether text is displayed as **normal, italic, or oblique**.

Syntax:

```css
selector {
  font-style: value;
}
```

| Value     | Appearance      |
| --------- | --------------- |
| `normal`  | Regular         |
| `italic`  | Italic typeface |
| `oblique` | Slanted type    |

---

## Font Size

The `font-size` property controls **how large or small text appears**.

Syntax:

```css
selector {
  font-size: value;
}
```

Example:

```css
h1 {
  font-size: 40px;
}
```

### Common Units

Font sizes can be specified using different units.

1. Pixels - `font-size: 16px;`
2. Relative `em` - `font-size: 1.5em;`
3. Relative `rem` - `font-size: 1.5rem;`
4. Percentage - `font-size: 120%;

---

## Font Weight

The `font-weight` property controls **how thick or bold the text appears**.

Syntax:

```css
selector {
  font-weight: value;
}
```

### Common Values

```css
font-weight: normal;
font-weight: bold;
font-weight: lighter;
font-weight: bolder;
```

Font weight can also be represented using numbers.

```css
font-weight: 100;
font-weight: 200;
font-weight: 300;
font-weight: 400;
font-weight: 500;
font-weight: 600;
font-weight: 700;
font-weight: 800;
font-weight: 900;
```

Generally:

```text
100 ───────────────→ 900
thin                 thick
```

### Font Shorthand

CSS provides a shorthand property called `font`. Instead of writing several font properties separately, we can combine them into one declaration.

#### Individual Properties

```css
p {
  font-style: italic;
  font-weight: bold;
  font-size: 18px;
  font-family: Arial, sans-serif;
}
```

#### Using `font` Shorthand

```css
p {
  font:
    italic bold 18px Arial,
    sans-serif;
}
```

A simplified structure is:

```text
font:
    style
    weight
    size
    family
```

🚨 Important: When using the `font` shorthand, **`font-size` and `font-family` are required**.

---

## Google Fonts

**Google Fonts** is a collection of fonts that can be used on websites. Instead of depending only on fonts installed on the user's computer, we can load a web font and use it in our website.Fonts can affect:

- Readability
- Visual hierarchy
- Branding
- Overall design
- User experience

For example, suppose we want to use **Roboto**. We can import the font into our CSS:

```css
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

body {
  font-family: "Roboto", sans-serif;
}
```

### Using Google Fonts Through HTML

Another common method is adding a `<link>` inside the `<head>` of the HTML document.

```html
<head>
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto&display=swap"
    rel="stylesheet"
  />
</head>
```

Then use it in CSS:

```css
body {
  font-family: "Roboto", sans-serif;
}
```

Example:

```css
h1 {
  font-family: "Roboto", sans-serif;
}

p {
  font-family: Georgia, serif;
}
```

Different parts of the page can use different fonts.

---

## Font Variant

The `font-variant` property controls **alternative variations of a font**.

1. Small Caps - Small caps display lowercase letters as **smaller capital letters**. Lowercase letters are rendered as **smaller versions of capital letters**.
2. Normal Font Variant - This displays the normal font variant.

```css
.normal {
  font-variant: normal;
}

.small {
  font-variant: small-caps;
}
```

---

## Quick Summary

**Font Family - Chooses the typeface.**
**Font Style - Controls normal, italic, or oblique text.**
**Font Size - Controls how large the text is.**
**Font Weight - Controls how thick the text appears.**
**Font Shorthand - Combines several font properties into one declaration.**
**Google Fonts - Allows to use web fonts.**
**Font Variant - Controls alternative font variations such as small caps.**

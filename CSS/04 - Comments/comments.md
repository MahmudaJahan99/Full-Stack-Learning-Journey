# CSS Comments

> **CSS comments** are notes written inside a CSS stylesheet that are **ignored by the browser**. They are useful for explaining code, organizing styles, leaving reminders, or temporarily disabling CSS rules.

CSS comments are written between:

```css
/* comment */
```

The browser does not apply anything written inside the comment.

## Basic CSS Comment

The comment is only for developers. A single-line comment can be written like this:

```css
/* This is a CSS comment */

p {
  color: blue;
}
```

```text
Browser
   |
   ↓
Reads CSS
   |
   ├── Comment → Ignored
   |
   └── CSS Rule → Applied
```

## Multi-line Comments

CSS does not have a separate syntax for single-line and multi-line comments. The same `/* */` syntax can contain multiple lines. Everything between `/*` and `*/` is treated as a comment.

```css
/*
    This section contains
    the styles for the
    main navigation.
*/

.navbar {
  display: flex;
  align-items: center;
}
```

---

## Useful Ways to Use CSS Comments

### 1. Explain Complex Code

```css
/* Center the card horizontally and vertically */
.card {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

### 2. Organize a Stylesheet

```css
/* =========================
   Header
   ========================= */

.header {
    ...
}


/* =========================
   Main Content
   ========================= */

.main {
    ...
}


/* =========================
   Footer
   ========================= */

.footer {
    ...
}
```

Comments can make large stylesheets easier to navigate.

### 3. Leave Development Notes

```css
/* TODO: Improve mobile spacing */
.container {
  padding: 40px;
}
```

### 4. Temporarily Disable Styles

```css
.card {
  width: 300px;
  /* box-shadow: 0 5px 15px gray; */
}
```

This allows you to test how the page looks without the `box-shadow`.

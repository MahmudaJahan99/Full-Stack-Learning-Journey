# CSS Basics

CSS can be added to an HTML document in different ways. These methods differ mainly in **where the CSS rules are written** and how reusable they are. The three basic methods are:

```text
CSS
 |
 ├── Inline CSS
 |
 ├── Internal CSS
 |
 └── External CSS
```

When multiple CSS rules affect the same element, the browser also needs a way to determine **which rule should be applied**. This is where the **cascading order** becomes important.

---

## Inline CSS

**Inline CSS** is CSS written directly inside an HTML element using the `style` attribute.

Example:

```html
<p style="font-size: 20px; color: gray;">Welcome to my website.</p>
```

The CSS is written directly on the element it affects. Multiple CSS declarations can be written inside the same `style` attribute:

### Advantages

- Quick to write
- Useful for small, one-off styles
- Easy to see which style is directly applied to an element

### Disadvantages

- Difficult to maintain in larger projects
- Styles cannot be easily reused
- Makes HTML harder to read
- Mixes content/structure with presentation
- Can lead to repetitive code

---

## Internal CSS

**Internal CSS** is CSS written inside a `<style>` element, usually within the `<head>` of an HTML document.

Example:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color: blue;
      }

      p {
        font-size: 18px;
      }
    </style>
  </head>

  <body>
    <h1>Hello World</h1>
    <p>Welcome to my website.</p>
  </body>
</html>
```

The browser reads these CSS rules and applies them to matching elements on that page.

### Advantages

- Keeps CSS separate from individual HTML elements
- Easier to organize than inline CSS
- Useful for page-specific styling
- No additional CSS file is required

### Disadvantages

- Styles cannot be easily shared between multiple HTML pages
- Large `<style>` sections can make HTML files difficult to maintain
- The CSS is tied to that particular HTML document

---

## External CSS

**External CSS** means writing CSS in a separate `.css` file and connecting it to the HTML document.

Example:

```text
project/
│
├── index.html
└── style.css
```

The CSS is written inside `style.css`:

```css
h1 {
  color: blue;
}

p {
  font-size: 18px;
}
```

The CSS file is then linked from the HTML document using the `<link>` element:

```html
<head>
  <link rel="stylesheet" href="style.css" />
</head>
```

### Advantages

- CSS is separated from HTML
- Styles can be reused across multiple pages
- Easier to maintain
- Keeps HTML cleaner
- Makes large projects easier to organize
- Browsers can cache external stylesheets

### Disadvantages

- Requires an additional file
- The stylesheet must be correctly linked
- Incorrect file paths can prevent the styles from loading

---

## Comparing the Three Methods

```text
┌──────────────────┬───────────────────────┬─────────────────────────┐
│ Method           │ CSS Location          │ Typical Use             │
├──────────────────┼───────────────────────┼─────────────────────────┤
│ Inline CSS       │ style attribute       │ One specific element    │
│ Internal CSS     │ <style> element       │ One HTML document       │
│ External CSS     │ Separate .css file    │ Multiple pages/projects │
└──────────────────┴───────────────────────┴─────────────────────────┘
```

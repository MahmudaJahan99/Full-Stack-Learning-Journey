# `id`

The `id` attribute gives an element a **unique identifier**.

```html
<p id="intro">Welcome to my website!</p>
```

The element now has the identifier: _intro_

---

## Why Use `id`?

An `id` can be used to identify a **specific element**.

For example:

```html
<h1 id="main-heading">My Portfolio</h1>
```

Now other parts of the webpage can refer specifically to this element.

An `id` is intended to identify one particular element within a document.

---

## Using `id` with CSS

An ID can be used as a CSS selector.

HTML:

```html
<h1 id="main-heading">My Portfolio</h1>
```

CSS:

```css
#main-heading {
  color: blue;
}
```

---

## Using `id` with Links

An ID can be used as the destination of a link. When the user clicks the link, the browser can jump to the element with specified ID.

```html
<a href="#projects"> View My Projects </a>

<h2 id="projects">My Projects</h2>
```

This is particularly useful for:

- Table of contents
- Long pages
- Section navigation
- "Back to top" links

---

## Using `id` with JavaScript

JavaScript can also find an element using its ID.

```html
<p id="message">Hello!</p>
```

```javascript
const message = document.getElementById("message");
```

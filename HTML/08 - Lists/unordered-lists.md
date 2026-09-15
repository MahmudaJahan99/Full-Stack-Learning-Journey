# Unordered Lists

An **unordered list** is used when the order of the items does **not** matter.

The HTML element for an ordered list is `<ul></ul>`.

Basic syntax:

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

The browser displays:

```text
• HTML
• CSS
• JavaScript
```

Use `<ul>` when the **sequence of the items isn't important**.

For example, a list of skills:

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>React</li>
</ul>
```

It doesn't matter whether HTML appears before CSS or JavaScript.

---

## Ordered vs Unordered Lists

```text
Does the order matter?
       │
   ┌───┴───┐
  YES      NO
   │        │
   ▼        ▼
  <ol>     <ul>
```

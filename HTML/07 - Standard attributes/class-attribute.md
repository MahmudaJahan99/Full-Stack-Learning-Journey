# `class`

The `class` attribute assigns one or more elements to a **class/group**. Unlike `id`, a class can be shared by many elements.

Example

```html
<p class="highlight">First paragraph</p>

<p class="highlight">Second paragraph</p>
```

Both elements belong to the `highlight` class.

## Why Use `class`?

Classes are commonly used to:

- Apply CSS styles to multiple elements
- Group related elements
- Identify elements for JavaScript
- Represent a reusable type/category

Example:

```html
<button class="button">Save</button>
<button class="button">Cancel</button>
<button class="button">Delete</button>
```

All three buttons can share the same CSS:

```css
.button {
  padding: 10px 20px;
}
```

## An Element Can Have Multiple Classes

An element can belong to more than one class. Classes are separated by spaces.

```text
class="button primary large"
       │       │       │
       ▼       ▼       ▼
    class 1  class 2  class 3
```

This element has three classes: _button_, _primary_, and _large_

---

## `class` vs `id`

| `id`                                    | `class`                 |
| --------------------------------------- | ----------------------- |
| Identifies a specific element           | Groups elements         |
| Intended to be unique within a document | Can be reused           |
| CSS selector uses `#`                   | CSS selector uses `.`   |
| Example: `id="header"`                  | Example: `class="card"` |

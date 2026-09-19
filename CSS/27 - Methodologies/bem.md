# BEM

> **BEM** stands for **Block — Element — Modifier**. It is a CSS naming methodology designed to make class names more predictable and maintainable. BEM does not change CSS itself. It gives a **convention for naming classes**.

BEM helps with:

- Predictable class names
- Large CSS organization
- Component identification
- Reducing naming ambiguity
- Understanding HTML/CSS relationships

## Block

A **block** is an independent UI component.

Examples:

```text
card
button
navbar
form
menu
```

## Element

An **element** is a part of a block.

Example:

```html
<div class="card">
  <h2 class="card__title">Product</h2>
  <p class="card__description">Product description</p>
</div>
```

Here:

```text
card
 │
 ├── card__title
 │
 └── card__description
```

The double underscore `__` represents an element.

## Modifier

A **modifier** represents a variation or state.

Example:

```html
<button class="button button--primary">Submit</button>
```

Here:

```text
button
   ↓
Block

button--primary
   ↓
Modifier
```

---

# BEM Mental Model

```text
BLOCK
 │
 ├── BLOCK__ELEMENT
 ├── BLOCK__ELEMENT
 │
 └── BLOCK--MODIFIER
```

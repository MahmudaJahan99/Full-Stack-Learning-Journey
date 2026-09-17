# CSS — Combinator Selectors

**Combinator selectors** are used to select elements based on their **relationship with other elements**. A **combinator** is a symbol or space that describes the relationship between two selectors.

While simple selectors help us select elements directly, combinators allow us to say things like:

_"Select the `<p>` inside this `<div>`."_ or _"Select the `<p>` immediately after this `<h2>`."_

---

## 1. Descendant Combinator

> The **descendant combinator** selects elements that are **inside another element**, at any level. It is represented by a **space**.

Syntax:

```css
parent child {
  property: value;
}
```

This select every `child` that exists somewhere inside `parent`. The `child` does **not** need to be a direct child.

Example:

```css
div p {
  color: blue;
}
```

---

# 2. Child Combinator

The **child combinator** selects an element that is a **direct child** of another element. It is represented by **`>`**

Syntax:

```css
parent > child {
  property: value;
}
```

This means select `child` only when it is directly inside `parent`.

Example:

```css
div > p {
  color: blue;
}
```

---

### Descendant vs Child

**`parent child`** selects **any `child` inside `parent`**.
**`parent > child`** select only `child` elements that are **directly inside `parent`**.

```text
div p
│
└── anywhere inside

div > p
│
└── directly inside
```

---

## 3. Next Sibling Combinator

> The **next sibling combinator** selects an element that comes **immediately after another element**. It is represented by **`+`**

Syntax:

```css
element1 + element2 {
  property: value;
}
```

The `+` combinator cares about the **immediately following sibling**. This means select `element2` only if it comes immediately after `element1`.

Example:

```css
h2 + p {
  color: blue;
}
```

---

## 4. Subsequent Sibling Combinator

> The **subsequent sibling combinator** selects **all matching siblings that come after an element**. It is represented by **`~`**

Syntax:

```css
element1 ~ element2 {
  property: value;
}
```

This means select all `element2` elements that appear after `element1` and share the same parent.

Example

```css
h2 ~ p {
  color: blue;
}
```

It selects matching siblings that appear later, even if other elements are between them.

---

## Think in Terms of the HTML Tree

Combinators become much easier when we think about **relationships**.

```text
<div class="container">
│
├── <p> Paragraph 1
│
├── <section>
│     │
│     └── <p> Paragraph 2
│
├── <p> Paragraph 3
│
└── <p> Paragraph 4
```

### Descendant

```css
.container p
```

Looks **downward anywhere**.

```text
.container
     │
     ├── p ✓
     │
     └── section
           └── p ✓
```

### Child

```css
.container > p
```

Looks for **direct children only**.

```text
.container
     │
     ├── p ✓
     │
     └── section
           └── p ✗
```

### Next Sibling

```css
section + p
```

Looks at the **immediately following sibling**.

```text
section
   │
   ▼
   p ✓
```

### Subsequent Sibling

```css
section ~ p
```

Looks at **all matching siblings that follow**.

```text
section
   │
   ├── p ✓
   └── p ✓
```

---

| Combinator             | Example   | Meaning                               |
| ---------------------- | --------- | ------------------------------------- |
| **Descendant**         | `div p`   | All `<p>` inside `<div>` at any level |
| **Child**              | `div > p` | `<p>` directly inside `<div>`         |
| **Next sibling**       | `h2 + p`  | `<p>` immediately after `<h2>`        |
| **Subsequent sibling** | `h2 ~ p`  | All `<p>` siblings after `<h2>`       |

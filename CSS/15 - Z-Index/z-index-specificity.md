# CSS — z-index & Stacking Context

When multiple HTML elements overlap, CSS needs to decide **which element should appear in front of the others**. This is where **`z-index`** and **stacking contexts** become important. `z-index` is most commonly used with **positioned elements**.

---

## `z-index`

The **`z-index`** property controls the **stacking order** of elements.

Think of overlapping elements as layers:

```text
        ┌───────────────┐
        │   Element C   │  ← z-index: 3 (front)
        └───────────────┘

      ┌───────────────────┐
      │    Element B      │  ← z-index: 2
      └───────────────────┘

    ┌─────────────────────────┐
    │       Element A         │  ← z-index: 1 (back)
    └─────────────────────────┘
```

A **higher `z-index` generally places an element above another element within the same stacking context**.

### Positive and Negative `z-index`

`z-index` can use:

- Positive values
- `0`
- Negative values

Example:

```css
.box1 {
  z-index: 1;
}

.box2 {
  z-index: 5;
}

.box3 {
  z-index: -1;
}
```

Conceptually:

```text
Higher z-index
      ↑
      │
   5  │  box2
   1  │  box1
   0  │  normal layer
  -1  │  box3
      │
      ↓
Lower z-index
```

However, `z-index` does **not** simply compare every element on the page globally. The stacking context in which an element exists matters.

### `z-index: 0`

`z-index: 0` places an element at the default stacking level within its stacking context. It can be useful when explicitly establishing an element's stacking level.

```css
.box {
  position: relative;
  z-index: 0;
}
```

### `z-index: auto`

`auto` means the element participates in the normal stacking order rather than being assigned a specific integer stacking level. The default value of `z-index` is `auto`.

```css
.box {
  z-index: auto;
}
```

---

## Stacking

**Stacking** is the way browsers determine which elements appear **in front of or behind other elements** when they overlap. The browser uses a **stacking order** to determine this layering. `z-index` can influence that order.

### Stacking Context

A **stacking context** is an independent group of elements that the browser treats as a separate **layering environment**. Elements inside one stacking context are stacked **within that context**.

A very large `z-index` does not automatically put an element above everything on the page.

For example:

```css
.parent {
  position: relative;
  z-index: 1;
}

.child {
  position: absolute;
  z-index: 9999;
}
```

The child has `z-index: 9999`. But it is still inside the parent's stacking context.

Another element might belong to a different stacking context:

```css
.other {
  position: relative;
  z-index: 2;
}
```

Conceptually:

```text
Page
│
├── Parent Context
│     └── Child
│          z-index: 9999
│
└── Other Context
      z-index: 2
```

The child cannot simply escape its parent's stacking context because its `z-index` is larger.

---

## `z-index` Does Not Affect Normal Layout

`z-index` controls **layering**, not the physical layout of elements. It only affects which element appears in front when elements overlap. Increasing `z-index` does **not**:

- Move the element
- Increase its width
- Increase its height
- Create margin
- Create padding

---

> **`z-index` controls stacking order, while stacking contexts define the boundaries within which that stacking order is resolved.**

---

# Flexbox

**Flexbox** is a one-dimensional CSS layout system. It is designed for arranging elements along **one main direction**

Flexbox is especially useful for:

- Navigation bars
- Button groups
- Cards in a row
- Centering elements
- Aligning items
- Responsive components

## Flex Container

To use Flexbox, make an element a flex container:

```css
.container {
  display: flex;
}
```

Its direct children become **flex items**.

```html
<div class="container">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

```text
Flex Container
┌──────────────────────────┐
│ Item 1 │ Item 2 │ Item 3 │
└──────────────────────────┘
```

## `flex-direction`

Controls the main direction of flex items.

Values:

```css
flex-direction: row;
flex-direction: row-reverse;
flex-direction: column;
flex-direction: column-reverse;
```

## Main Axis and Cross Axis

The **main axis** follows the `flex-direction`.

The **cross axis** runs perpendicular to it.

### `row`

```text
Main Axis →
────────────────────────────

        Cross Axis
             ↓
```

### `column`

```text
Cross Axis →
────────────────────────────

Main Axis
    ↓
```

So:

```text
flex-direction: row
        ↓
main axis = horizontal


flex-direction: column
        ↓
main axis = vertical
```

## `justify-content`

`justify-content` controls how flex items are distributed along the **main axis**.

Values:

```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: center;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

## `align-items`

`align-items` controls alignment along the **cross axis**.

Values:

```css
align-items: stretch;
align-items: flex-start;
align-items: flex-end;
align-items: center;
align-items: baseline;
```

## `flex-wrap`

By default, flex items try to stay on one line.

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

When there isn't enough space, items can move onto additional lines.

```text
┌──────────────────────────────┐
│ Box 1 │ Box 2 │ Box 3        │
│ Box 4 │ Box 5 │ Box 6        │
└──────────────────────────────┘
```

Values:

```css
flex-wrap: nowrap;
flex-wrap: wrap;
flex-wrap: wrap-reverse;
```

## `gap`

`gap` creates space between flex items. Instead of manually adding margins between every item, `gap` provides consistent spacing.

---

## Flex Item Properties

Some properties are applied to the **children** of a flex container.

### `flex-grow`

Controls how much an item can grow when extra space is available.

```css
.item {
  flex-grow: 1;
}
```

### `flex-shrink`

Controls how much an item can shrink when there isn't enough space.

```css
.item {
  flex-shrink: 1;
}
```

### `flex-basis`

Defines the initial size of a flex item along the main axis.

```css
.item {
  flex-basis: 200px;
}
```

---

# 31. `flex` Shorthand

These properties can be combined. A common use is to allow items to share available space.

```css
.item {
  flex: 1;
}
```

---

# Centering with Flexbox

One of the most common Flexbox patterns is centering an element.

```css
.container {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

This centers the items along both axes when the container has the appropriate available space.

```text
┌─────────────────────────────┐
│                             │
│          ┌────────┐         │
│          │  Item  │         │
│          └────────┘         │
│                             │
└─────────────────────────────┘
```

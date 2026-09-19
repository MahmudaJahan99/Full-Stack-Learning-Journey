# Grid

**CSS Grid** is a two-dimensional layout system. It allows you to control both _rows_ and _columns_.

## Creating a Grid

Make an element a grid container. Then define columns.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

This creates three equal columns.

```text
┌────────┬────────┬────────┐
│        │        │        │
│ Item 1 │ Item 2 │ Item 3 │
│        │        │        │
└────────┴────────┴────────┘
```

## `grid-template-columns`

Defines the columns of a grid.

```css
.container {
  grid-template-columns: 200px 200px 200px;
}
```

We can also use flexible units:

```css
.container {
  grid-template-columns: 1fr 1fr 1fr;
}
```

Or different sizes:

```css
.container {
  grid-template-columns: 200px 1fr 2fr;
}
```

## The `fr` Unit

`fr` means **fraction of the available space** in a grid container.

Example:

```css
.container {
  grid-template-columns: 1fr 1fr;
}
```

The available space is divided equally.

```text
┌──────────────────┬──────────────────┐
│       1fr        │       1fr        │
└──────────────────┴──────────────────┘
```

## `grid-template-rows`

Defines grid rows.

```css
.container {
  grid-template-rows: 100px 200px;
}
```

## Grid `gap`

`gap` creates space between rows and columns.

```css
.container {
  display: grid;
  gap: 20px;
}
```

We can also control them separately:

```css
.container {
  row-gap: 20px;
  column-gap: 30px;
}
```

---

## Grid Items

The direct children of a grid container become **grid items**.

```html
<div class="grid">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}
```

Result:

```text
┌──────────────┬──────────────┐
│    Item 1    │    Item 2    │
├──────────────┼──────────────┤
│    Item 3    │    Item 4    │
└──────────────┴──────────────┘
```

## `repeat()`

Instead of writing:

```css
grid-template-columns: 1fr 1fr 1fr;
```

we can write:

```css
grid-template-columns: repeat(3, 1fr);
```

This means 3 columns, each taking `1fr`.

---

# Responsive Grid

Grid works very well with responsive layouts. A common pattern is:

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}
```

On smaller screens, we can change the number of columns with a media query:

```css
@media (max-width: 768px) {
  .container {
    grid-template-columns: 1fr;
  }
}
```

Desktop:

```text
┌──────┬──────┬──────┐
│  1   │  2   │  3   │
└──────┴──────┴──────┘
```

Mobile:

```text
┌──────────────┐
│      1       │
├──────────────┤
│      2       │
├──────────────┤
│      3       │
└──────────────┘
```

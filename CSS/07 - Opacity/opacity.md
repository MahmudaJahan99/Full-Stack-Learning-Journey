# CSS — Opacity

The CSS `opacity` property controls **how transparent or visible an element is**.

An element with:

- `opacity: 1` → completely visible
- `opacity: 0` → completely transparent
- A value between `0` and `1` → partially transparent

## Basic Syntax

```css
selector {
  opacity: value;
}
```

The value ranges from:

```text
0 ─────────────────── 1
│                      │
Transparent          Visible
```

Example:

```css
.box {
  opacity: 0.5;
}
```

The element becomes **50% visible / 50% transparent**.

## Common Opacity Values

| Opacity | Visibility             |
| ------: | ---------------------- |
|     `1` | 100% visible           |
|   `0.8` | 80% visible            |
|   `0.5` | 50% visible            |
|   `0.2` | 20% visible            |
|     `0` | Completely transparent |

---

## Opacity Affects the Whole Element

One important thing to remember is that `opacity` affects the **entire element and its contents**.

Example:

```html
<div class="card">
  <h2>Hello</h2>
  <p>This is a card.</p>
</div>
```

```css
.card {
  opacity: 0.5;
}
```

The transparency applies to:

```text
.card
  │
  ├── background
  ├── border
  ├── <h2>
  └── <p>
```

So the text, background, border, images, and other content inside the element are also affected.

---

## Opacity vs Transparent Color

Opacity is different from making **only a background color transparent**.

Example:

```css
.card {
  opacity: 0.5;
}
```

This makes the **whole card** transparent.

But if we use a color with transparency:

```css
.card {
  background-color: rgba(0, 0, 0, 0.5);
}
```

the transparency is applied to the **background color**, while the content can remain fully visible.

This distinction becomes useful when designing overlays, cards, menus, and other UI elements.

---

## Opacity on Images

Opacity can also be applied to images.

```html
<img src="image.jpg" class="image" alt="A landscape" />
```

```css
.image {
  opacity: 0.6;
}
```

The image becomes partially transparent.

---

## Opacity on Hover

Opacity is commonly used with the `:hover` pseudo-class to create simple visual effects.

```css
button {
  opacity: 1;
}

button:hover {
  opacity: 0.7;
}
```

This creates a simple visual indication that the element is interactive.

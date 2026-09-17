# CSS — Width & Height

The CSS `width` and `height` properties control the **dimensions of an element**.

```css
.box {
  width: 300px;
  height: 200px;
}
```

- `width: 300px` → controls the horizontal dimension
- `height: 200px` → controls the vertical dimension

---

## Width

The `width` property sets the width of an element.

Example:

```css
.box {
  width: 300px;
}
```

The element's width is set to `300px`.

```text id="c6v3yt"
        ←──── 300px ────→

       ┌─────────────────┐
       │                 │
       │       BOX       │
       │                 │
       └─────────────────┘
```

---

## Height

The `height` property sets the height of an element.

Example:

```css
.box {
  height: 200px;
}
```

The element's height is set to `200px`.

```text
       ┌───────────────┐
       │               │
       │               │
       │      BOX      │ ↑
       │               │ │ 200px
       │               │ ↓
       └───────────────┘
```

---

## Width and Height Together

```css
.box {
  width: 300px;
  height: 200px;
}
```

Conceptually:

```text
          300px
    ←──────────────→
    ┌──────────────┐
    │              │
    │              │
200px              │
    │              │
    │              │
    └──────────────┘
```

---

### Different Units

Width and height can use different CSS units.

Common units include:

- `px`
- `%`
- `em`
- `rem`
- `vw`
- `vh`
- `auto`

---

## Width/Height and the Box Model

🚨 An important point: `width` and `height` do not always represent the entire visible size of an element. This depends on the `box-sizing` property.

By default:

```css
box-sizing: content-box;
```

With `content-box`, the declared width and height apply to the **content area**.

For example:

```css
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
}
```

The content width is **300px**.

But the total width becomes:

```text
Content       = 300px
Left padding  = 20px
Right padding = 20px
Left border   = 5px
Right border  = 5px

Total         = 350px
```

---

## `box-sizing: border-box`

With `box-sizing: border-box;`, the declared width includes _Content_, _Padding_, and _Border_

Example:

```css id="v6p2kc"
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

Now the **entire box remains 300px wide**.

This is why `box-sizing` is important when working with element dimensions.

---

### `min-width` and `max-width`

CSS also provides limits for an element's width.

#### `min-width`

Sets the minimum width an element can have.

```css
.box {
  min-width: 300px;
}
```

The element should not become narrower than `300px`.

#### `max-width`

Sets the maximum width.

```css
.box {
  max-width: 800px;
}
```

The element should not become wider than `800px`.

---

### `min-height` and `max-height`

The same concept applies to height. CSS provides limits for an element's height.

#### `min-height`

```css
.box {
  min-height: 200px;
}
```

The element should not become shorter than `200px`.

#### `max-height`

```css
.box {
  max-height: 500px;
}
```

The element should not become taller than `500px`.

# `visibility`

The `visibility` property controls whether an element is **visible or hidden**. The main values are `visible` and `hidden`.

By default `visibility: visible;`. The element is visible.

## `visibility: hidden`

`visibility: hidden` makes an element invisible **but keeps its space in the layout**.

Example:

```css
.box {
  visibility: hidden;
}
```

Conceptually:

```text
Before:

┌──────────────┐
│    BOX 1     │
└──────────────┘
┌──────────────┐
│    BOX 2     │
└──────────────┘
┌──────────────┐
│    BOX 3     │
└──────────────┘


visibility: hidden

┌──────────────┐
│    BOX 1     │
└──────────────┘

      [space]

┌──────────────┐
│    BOX 3     │
└──────────────┘
```

Box 2 is invisible, but its layout space remains.

---

## `display` vs `visibility`

| Property     | Value          | Visible? | Takes Space? |
| ------------ | -------------- | -------: | -----------: |
| `display`    | `block`        |      Yes |          Yes |
| `display`    | `inline`       |      Yes |          Yes |
| `display`    | `inline-block` |      Yes |          Yes |
| `display`    | `none`         |       No |           No |
| `visibility` | `visible`      |      Yes |          Yes |
| `visibility` | `hidden`       |       No |          Yes |

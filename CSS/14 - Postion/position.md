# CSS Position

The CSS `position` property controls **how an element is positioned in a document**. The main values are:

- static
- relative
- absolute
- fixed
- sticky

Once an element has a positioning value other than `static`, properties such as `top`, `right`, `bottom`, and `left` can be used to control its position.

## `position: static`

`static` is the **default positioning** for HTML elements. The element stays in the **normal document flow**.

```css
.box {
  position: static;
}
```

The browser places the elements according to the normal layout rules.

The `top`, `right`, `bottom`, and `left` values have no effect.

---

## `position: relative`

`relative` keeps the element in the **normal document flow**, but allows us to move it relative to its **original position**.

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```

The element moves:

```text
Original position
┌──────────────┐
│     BOX      │
└──────────────┘
      ↓
   top: 20px
      ↓
        ┌──────────────┐
        │     BOX      │
        └──────────────┘
             →
          left: 30px
```

When we move a relatively positioned element, its **original space is still reserved**. This is one of the biggest differences between `relative` and `absolute`.

---

## `position: absolute`

`absolute` removes the element from the **normal document flow**. The element is positioned relative to its **nearest positioned ancestor**. If there is no suitable positioned ancestor, the element is generally positioned relative to the initial containing block.

```css
.box {
  position: absolute;
  top: 20px;
  left: 30px;
}
```

A positioned ancestor generally means an ancestor whose `position` is not `static`, such as:

```css
position: relative;
position: absolute;
position: fixed;
position: sticky;
```

---

### `top`, `right`, `bottom`, `left`

These properties are called **offset properties**.

Example:

```css
.box {
  position: absolute;
  top: 20px;
  right: 30px;
}
```

This positions the element:

```text
Parent
┌─────────────────────────────────┐
│                     30px ←      │
│                         ┌──────┐│
│                     20px↓ Box  ││
│                         └──────┘│
│                                 │
└─────────────────────────────────┘
```

---

## `position: fixed`

A fixed element is positioned relative to the **viewport**. It remains in the same place even when the page is scrolled.

```css
.button {
  position: fixed;
  bottom: 20px;
  right: 20px;
}
```

Conceptually:

```text
Browser viewport
┌────────────────────────────────┐
│                                │
│        Page content            │
│                                │
│                                │
│                                │
│                         ┌────┐ │
│                         │ ↑  │ │
│                         └────┘ │
└────────────────────────────────┘
                          ↑
                     fixed button
```

The button stays in that viewport position while the page scrolls.

Fixed positioning is commonly used for:

- Floating action buttons
- Back-to-top buttons
- Chat buttons
- Fixed navigation
- Cookie notices
- Persistent UI controls

Like absolutely positioned elements, fixed elements are removed from the normal document flow.

---

## `position: sticky`

`sticky` is a combination of **normal-flow behavior and fixed-like behavior**. An element initially behaves normally, but when scrolling reaches a specified offset, it can stick within its scrolling container.

Example:

```css
.header {
  position: sticky;
  top: 0;
}
```

Conceptually:

```text
Before scrolling:

┌─────────────────────────┐
│ Header                  │
├─────────────────────────┤
│ Content                 │
│ Content                 │
│ Content                 │
└─────────────────────────┘


After scrolling:

┌─────────────────────────┐
│ Header ← stays at top   │
├─────────────────────────┤
│ Content                 │
│ Content                 │
│ Content                 │
└─────────────────────────┘
```

The header sticks when it reaches `top: 0`.

### Sticky Requires an Offset

A sticky element usually needs an offset such as:

```css
position: sticky;
top: 0;
```

or:

```css
position: sticky;
bottom: 0;
```

Without an appropriate inset/offset, the sticky behavior may not produce the effect we expect.

---

### Sticky vs Fixed

These two are commonly confused.

### Fixed

```css
position: fixed;
top: 0;
```

The element is attached to the viewport.

---

### Position Values Comparison

| Position   | Normal Flow?  | Positioned Relative To                 | Scroll Behavior              |
| ---------- | ------------- | -------------------------------------- | ---------------------------- |
| `static`   | Yes           | Normal layout                          | Normal                       |
| `relative` | Yes           | Its original position                  | Scrolls normally             |
| `absolute` | No            | Nearest positioned ancestor            | Scrolls with document        |
| `fixed`    | No            | Viewport                               | Stays fixed during scrolling |
| `sticky`   | Yes initially | Its scrolling context/containing block | Becomes stuck at an offset   |

---

## `z-index` with Positioned Elements

Positioning is often used together with `z-index` to control which element appears in front. A higher stacking level can place an element above another element when the relevant stacking contexts allow it.

```css
.modal {
  position: fixed;
  z-index: 1000;
}
```

Example:

```text
Page
┌─────────────────────────┐
│                         │
│       Content           │
│                         │
│   ┌───────────────┐     │
│   │     MODAL     │ ← higher stacking level
│   └───────────────┘     │
│                         │
└─────────────────────────┘
```

`z-index` is a related concept to positioning, but the important point here is positioning is often used when elements need to overlap or appear above other content.

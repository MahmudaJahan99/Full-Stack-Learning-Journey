# CSS Display

The CSS `display` property controls **how an HTML element is displayed and how it participates in the layout**.

---

## `display: block`

A **block-level element** normally starts on a new line and takes up the available width. Common block-level elements include:

```html
<div>...</div>
<p>...</p>
<h1>...</h1>
<section>...</section>
<header>...</header>
<footer>...</footer>
```

Each block normally occupies its own line.

```text
┌────────────────────────────────────┐
│              DIV                   │
└────────────────────────────────────┘
┌────────────────────────────────────┐
│              P                     │
└────────────────────────────────────┘
```

Block elements normally allows to control `width`, `height`, `margin`, and `padding`.
A block element can have a specified width. If no width is specified, a block element generally stretches to fill the available width of its containing block.
For example:

```css
.box {
  width: 300px;
  height: 150px;
  padding: 20px;
  margin: 10px;
}
```

---

## `display: inline`

An **inline element** stays within the same line as surrounding content whenever there is enough horizontal space. Common inline elements include:

```html
<span>...</span>
<a href="#">...</a>
<strong>...</strong>
<em>...</em>
```

Example:

```html
<p>
  This is
  <span>inline text</span>
  inside a paragraph.
</p>
```

Conceptually:

```text
This is [inline text] inside a paragraph.
```

The inline element does not automatically start a new line.

### Width and Height with Inline Elements

A very important characteristic of inline elements is that `width` and `height` generally do **not** work in the same way they do for block-level elements. The specified `width` and `height` do not control the inline element's layout dimensions as they would for a block or inline-block element. The element generally follows the dimensions required by its content.

Example:

```css
span {
  display: inline;
  width: 300px;
  height: 100px;
}
```

### Padding and Margin with Inline Elements

Inline elements can have horizontal padding and margins. However, vertical layout behavior can be different from block-level elements.

Example:

```css
span {
  display: inline;
  padding: 10px;
  margin: 10px;
}
```

---

## `display: inline-block`

`inline-block` combines characteristics of **inline** and **block** elements. It:

- Stays on the same line as other inline/inline-block elements when space is available.
- Allows `width` and `height`.
- Allows normal box-model sizing such as padding and borders.

Example:

```css
.box {
  display: inline-block;
  width: 150px;
  height: 100px;
}
```

Conceptually:

```text
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│    BOX 1     │  │    BOX 2     │  │    BOX 3     │
│              │  │              │  │              │
└──────────────┘  └──────────────┘  └──────────────┘
```

They can sit beside each other while still behaving like boxes.

---

## `display: none`

`display: none` completely removes an element from the layout.

Example:

```css
.hidden {
  display: none;
}
```

HTML:

```html
<p>Hello</p>

<p class="hidden">You cannot see me.</p>

<p>Goodbye</p>
```

The hidden element does not appear and does not occupy space.

```text
Before:

┌──────────────┐
│    Hello     │
└──────────────┘
┌──────────────┐
│    Hidden    │id
└──────────────┘
┌──────────────┐
│   Goodbye    │
└──────────────┘


display: none

┌──────────────┐
│    Hello     │
└──────────────┘
┌──────────────┐
│   Goodbye    │
└──────────────┘
```

The hidden element's space disappears completely.

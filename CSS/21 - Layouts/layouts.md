# Layouts

CSS layout is the system that determines **how elements are arranged on a webpage**. HTML provides the structure. CSS determines how those elements are positioned and arranged:

Layout controls things such as:

- Where elements appear
- How much space they occupy
- How elements interact with each other
- How elements are arranged horizontally or vertically
- How layouts respond to different screen sizes

---

## Flow Layout

**Flow layout** is the default way that elements are arranged on a webpage. When we write HTML without using special layout techniques such as Flexbox or Grid, the browser places elements according to the **normal flow**.

The exact layout depends on whether elements are block-level or inline.

### Block-Level Elements in Flow

Block-level elements normally start on a **new line** and take up the available width. Examples include:

```html
<div></div>
<p></p>
<h1></h1>
<section></section>
<header></header>
<footer></footer>
```

Each block normally occupies its own line.

### Inline Elements in Flow

Inline elements normally remain on the same line as surrounding text when there is enough space. Examples include:

```html
<span></span>
<a></a>
<strong></strong>
<em></em>
```

The elements participate in the same line of text. If there isn't enough horizontal space, inline content can wrap onto another line.

### Normal Flow and the Box Model

Flow layout works together with the CSS box model.

An element's:

- Content
- Padding
- Border
- Margin

all affect the space it occupies.

### Normal Flow and `position`

Some positioning methods change how an element participates in normal flow.

1. `position: static` - This is the default. The element remains in normal flow.
2. `position: relative` - The element remains part of the normal flow, even though it is visually moved.
3. `position: absolute` - The element is removed from normal flow.
4. `position: fixed` - The element is also removed from normal flow and positioned relative to the viewport.

---

#3 Flexbox vs Grid

| Feature                 | Flexbox         | Grid             |
| ----------------------- | --------------- | ---------------- |
| Dimension               | One-dimensional | Two-dimensional  |
| Main focus              | Row or column   | Rows and columns |
| Alignment               | Excellent       | Excellent        |
| Navigation bars         | Very useful     | Possible         |
| Card rows               | Very useful     | Very useful      |
| Complex page layouts    | Possible        | Excellent        |
| Rows + columns together | Less suitable   | Excellent        |
| Content-driven layouts  | Excellent       | Excellent        |
| Page structure          | Possible        | Excellent        |

---

## Choosing the Right Layout Technique

### Use normal flow when:

- Content naturally follows one element after another
- You are building ordinary document content
- No special layout system is required

### Use float when:

- Text needs to wrap around an element
- Working with certain legacy layouts

### Use Multicolumn when:

- Long text should flow through multiple columns
- Creating newspaper/magazine-style content

### Use Flexbox when:

- You are arranging items in one direction
- You need easy alignment
- You are building navigation bars or component-level layouts

### Use Grid when:

- You need rows and columns
- You are creating a larger page structure
- You need precise two-dimensional layout

# CSS Box Model

Every HTML element on a webpage is treated by the browser as a **rectangular box**. The **CSS Box Model** describes how the size of that box is calculated and how space is added around its content.

Every element consists of four main parts:

```text
              CSS BOX MODEL

        ┌───────────────────────────────┐
        │            MARGIN             │
        │   ┌───────────────────────┐   │
        │   │        BORDER         │   │
        │   │   ┌───────────────┐   │   │
        │   │   │    PADDING    │   │   │
        │   │   │  ┌─────────┐  │   │   │
        │   │   │  │ CONTENT │  │   │   │
        │   │   │  └─────────┘  │   │   │
        │   │   └───────────────┘   │   │
        │   └───────────────────────┘   │
        └───────────────────────────────┘

        Margin → Border → Padding → Content
```

> **Content** = what's inside
> **Padding** = space inside the box
> **Border** = the box's edge
> **Margin** = space outside the box

---

## 1. Content

The **content** is the actual material inside an element. The content area can contain:

- Text
- Images
- Other HTML elements
- Buttons
- Forms
- etc.

We can control the content area's dimensions using **`width`** and **`height`**.

---

## 2. Padding

**Padding** is the space **between the content and the border**. Padding prevents content from touching the border.

```css
.box {
  padding: 20px;
}
```

### Padding on Individual Sides

We can control each side separately.

```css
.box {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 30px;
  padding-left: 40px;
}
```

### Padding Shorthand

Instead of writing four separate properties, we can use the `padding` shorthand.

#### One Value

```css
.box {
  padding: 20px;
}
```

All four sides receive `20px`.

Equivalent to:

```css
.box {
  padding-top: 20px;
  padding-right: 20px;
  padding-bottom: 20px;
  padding-left: 20px;
}
```

#### Two Values

```css
.box {
  padding: 10px 20px;
}
```

Means:

```text
10px → Top & Bottom
20px → Left & Right
```

Equivalent to:

```css
.box {
  padding-top: 10px;
  padding-right: 20px;
  padding-bottom: 10px;
  padding-left: 20px;
}
```

#### Three Values

```css
.box {
  padding: 10px 20px 30px;
}
```

Means:

```text
10px → Top
20px → Left & Right
30px → Bottom
```

Equivalent to:

```css
.box {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 20px;
}
```

#### Four Values

```css
.box {
  margin: 10px 20px 30px 40px;
}
```

The order is:

```text
Top → Right → Bottom → Left
```

---

## 3. Border

The **border** surrounds the padding and content.

```css
.box {
  border: 2px solid black;
}
```

A border has three main parts - _border-width_, _border-style_, and _border-color._

Example:

```css
.box {
  border-width: 2px;
  border-style: solid;
  border-color: black;
}
```

The shorthand is:

```css
.box {
  border: 2px solid black;
}
```

### Common border styles

```css
border-style: solid;
border-style: dashed;
border-style: dotted;
border-style: double;
```

---

## 4. Margin

**Margin** is the space **outside the border**. It creates distance between an element and surrounding elements.

```css
.card {
  margin: 20px;
}
```

### Margin on Individual Sides

We can control each side separately.

```css
.box {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 40px;
}
```

### Margin Shorthand

Instead of writing four separate properties, we can use the `margin` shorthand.

#### One Value

```css
.box {
  margin: 20px;
}
```

Applies to all four sides:

```text
           20px
             ↓
       ┌───────────┐
20px → │    BOX    │ ← 20px
       └───────────┘
             ↑
           20px
```

Equivalent to:

```css
.box {
  margin-top: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
  margin-left: 20px;
}
```

#### Two Values

```css
.box {
  margin: 10px 20px;
}
```

First value applies vertically and second value applies horizontally:

```text
         10px
           ↓
    ┌─────────────┐
20px│     BOX     │20px
    └─────────────┘
           ↑
         10px
```

Equivalent to:

```css
.box {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 10px;
  margin-left: 20px;
}
```

#### Three Values

```css
.box {
  margin: 10px 20px 30px;
}
```

First value applies to top, second value applies vertically, and third value applies to the bottom:

```text
         10px
           ↓
    ┌─────────────┐
20px│     BOX     │20px
    └─────────────┘
           ↑
         30px
```

Equivalent to:

```css
.box {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 20px;
}
```

#### Four Values

```css
.box {
  margin: 10px 20px 30px 40px;
}
```

The order is:

```text
Top → Right → Bottom → Left
```

---

### `margin: auto`

The `auto` value allows the browser to calculate the available margin automatically. A common use is horizontally centering a block element.

```css
.box {
  width: 300px;
  margin: 0 auto;
}
```

The browser distributes the available horizontal space between the left and right sides.

```text
┌─────────────────────────────────────┐
│                                     │
│         ┌───────────────┐           │
│         │      BOX      │           │
│         │     300px     │           │
│         └───────────────┘           │
│                                     │
└─────────────────────────────────────┘
       ← auto →       ← auto →
```

---

## 5. Width and Height

The `width` and `height` properties control the size of the element.

```css
.box {
  width: 300px;
  height: 200px;
}
```

But an important question is, **Does `width: 300px` mean the entire box is 300px wide?**

The answer depends on the value of `box-sizing`.

---

## Default Box Sizing

By default, CSS uses:

```css
box-sizing: content-box;
```

With `content-box`, the declared `width` and `height` apply to the **content area only**.

Example:

```css
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
}
```

The actual width becomes:

```text
Content width
300px

+ Left padding
20px

+ Right padding
20px

+ Left border
5px

+ Right border
5px

────────────────
Total = 350px
```

Margin is **not included** in the element's box width.

---

## `box-sizing: border-box`

`border-box` changes how width and height are calculated. Now the declared `width` and `height` apply to the **content, padding, and border**.

Example:

```css
.box {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  box-sizing: border-box;
}
```

The total box width remains 300px.

```text
Total width = 300px

┌──────────────────────────────┐
│          Border              │
│  ┌────────────────────────┐  │
│  │        Padding         │  │
│  │   ┌────────────────┐   │  │
│  │   │    Content     │   │  │
│  │   └────────────────┘   │  │
│  └────────────────────────┘  │
└──────────────────────────────┘
             300px
```

---

## `content-box` vs `border-box`

| Property                   | `content-box` | `border-box`               |
| -------------------------- | ------------- | -------------------------- |
| Declared width applies to  | Content       | Content + Padding + Border |
| Padding included in width? | No            | Yes                        |
| Border included in width?  | No            | Yes                        |
| Common default             | Yes           | No                         |

### Visual comparison

```text
content-box

width: 300px
     ↓
┌───────────────────────┐
│     Content 300px     │
└───────────────────────┘
   + padding + border


border-box

width: 300px
     ↓
┌───────────────────────┐
│ Content + Padding +   │
│ Border = 300px        │
└───────────────────────┘
```

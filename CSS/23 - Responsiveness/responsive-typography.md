# Responsive Typography

Responsive typography means allowing text to **adapt to different screen sizes**.

Responsive typography helps control:

- font size
- line height
- spacing
- readability

## Media Queries for Typography

One solution is to change the font size using media queries:

```css
h1 {
  font-size: 48px;
}

@media (max-width: 768px) {
  h1 {
    font-size: 32px;
  }
}
```

Now:

```text
Desktop → 48px
Mobile  → 32px
```

## Using Viewport Units

Viewport units allow font sizes to respond to the viewport. The font size changes as the viewport changes. `vw` means **viewport width**. So 1vw = 1% of viewport width.

```css
h1 {
  font-size: 5vw;
}
```

For example, if the viewport is `1000px` wide:

```text
5vw = 50px
```

If the viewport is `600px` wide:

```text
5vw = 30px
```

## `clamp()` for Responsive Typography

Using only `vw` can make text:

- too small on small screens
- too large on large screens

There is no built-in minimum or maximum. This is where `clamp()` becomes useful. The `clamp()` function allows us to define **minimum**, **preferred value**, and **maximum**.

Syntax:

```css
font-size: clamp(minimum, preferred, maximum);
```

Example:

```css
h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

This means:

```text
Minimum → 2rem
Preferred → 5vw
Maximum → 4rem
```

## Responsive Line Height

Font size isn't the only typography property that matters. Line height affects readability.

```css
p {
  line-height: 1.6;
}
```

Using a unitless value allows the line height to scale naturally with the element's font size.

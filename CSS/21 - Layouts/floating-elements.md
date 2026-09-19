# Floating Elements

The `float` property was originally designed to allow content such as text to flow around an element.

## `float: left`

```css
img {
  float: left;
  width: 200px;
  margin-right: 20px;
}
```

Conceptually:

```text
┌────────────┐  This is some text
│            │  that flows around
│   IMAGE    │  the floated image.
│            │
└────────────┘  More text continues
                below.
```

## `float: right`

```css
img {
  float: right;
}
```

Conceptually:

```text
Some text flows around
 the image           ┌────────────┐
                     │            │
                     │   IMAGE    │
                     │            │
                     └────────────┘
```

## `float: none`

The default value is `none`. The element does not float.

---

## Clearing Floats

When elements are floated, later content may need to be prevented from wrapping around them. The `clear` property controls this.

Possible values include:

```css
clear: left;
clear: right;
clear: both;
clear: none;
```

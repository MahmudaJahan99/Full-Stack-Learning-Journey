# Background Gradient

A gradient creates a **smooth transition between two or more colors**. Gradients are created using the `background-image` property.

There are two common types:

- `linear-gradient()`
- `radial-gradient()`

---

## Linear Gradient

A linear gradient changes colors along a straight line.

Syntax:

```css
background-image: linear-gradient(direction, color1, color2);
```

Example:

```css
.box {
  background-image: linear-gradient(red, blue);
}
```

### Changing the Direction

We can specify the direction of the gradient.

```css
.box {
  background-image: linear-gradient(to right, red, blue);
}
```

We can also use angles:

```css
.box {
  background-image: linear-gradient(45deg, red, blue);
}
```

### Multiple Colors

A gradient can contain more than two colors.

```css
.box {
  background-image: linear-gradient(to right, red, yellow, blue);
}
```

---

## Radial Gradient

A radial gradient spreads outward from a central point.

Syntax:

```css
background-image: radial-gradient(color1, color2);
```

Example:

```css
.box {
  background-image: radial-gradient(white, blue);
}
```

The color spreads outward from the center.

```text
        Blue
    Blue     Blue
   Blue White Blue
    Blue     Blue
        Blue
```

## Gradient as Background

A gradient is technically treated as a type of **background image**.

Therefore:

```css
background-image: linear-gradient(red, blue);
```

is used rather than:

```css
background-color: linear-gradient(red, blue);
```

---

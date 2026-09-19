# CSS Image Filters

CSS provides the `filter` property for applying visual effects to images and other elements.

Syntax:

```css
img {
  filter: filter-function(value);
}
```

## `filter: blur()`

The `blur()` function makes an image blurry. The larger the value, the stronger the blur.

```css
img {
  filter: blur(5px);
}
```

## `filter: brightness()`

Controls the brightness of an image.

```css
/* Normal brightness */
filter: brightness(100%);
```

```css
/* Darker */
filter: brightness(50%);
```

```css
/* Brighter */
filter: brightness(150%);
```

## `filter: contrast()`

Controls the contrast between light and dark areas.

```css
img {
  filter: contrast(150%);
}
```

`100%` represents the normal contrast level.

## `filter: grayscale()`

Converts an image to grayscale.

```css
img {
  filter: grayscale(100%);
}
```

## `filter: sepia()`

Creates a warm, old-photo-like appearance. The value is generally expressed as a percentage.

```css
img {
  filter: sepia(50%);
}
```

---

## `filter: saturate()`

Controls color intensity.

```css
/* Removes color saturation */
filter: saturate(0%);
```

```css
/* Normal saturation */
filter: saturate(100%);
```

```css
/* Makes colors more intense */
filter: saturate(200%);
```

## `filter: hue-rotate()`

Changes the colors of an image by rotating its hue around the color wheel. The value is measured in degrees.

```css
filter: hue-rotate(0deg);
filter: hue-rotate(90deg);
filter: hue-rotate(180deg);
```

This can produce dramatic color changes.

---

## `filter: invert()`

Inverts the colors of an image.

```css
img {
  filter: invert(100%);
}
```

For example:

```text
Black → White
White → Black
```

Partial inversion is also possible:

```css
filter: invert(50%);
```

## `filter: opacity()`

The `filter` function can also control opacity.

```css
img {
  filter: opacity(50%);
}
```

However, for ordinary opacity control, the `opacity` property is usually clearer:

## `filter: drop-shadow()`

`drop-shadow()` creates a shadow based on the visible shape of the element.

```css
img {
  filter: drop-shadow(5px 5px 5px gray);
}
```

This is especially useful for images with transparent backgrounds. For example, a transparent PNG can receive a shadow around its actual visible shape.

### Combining Filters

Multiple filter functions can be used together. The filters are applied in the order they are written.

```css
img {
  filter: grayscale(100%) brightness(120%) contrast(110%);
}
```

---

# Common Filter Functions

| Filter          | Purpose                   | Example                         |
| --------------- | ------------------------- | ------------------------------- |
| `blur()`        | Blurs the image           | `blur(5px)`                     |
| `brightness()`  | Changes brightness        | `brightness(150%)`              |
| `contrast()`    | Changes contrast          | `contrast(150%)`                |
| `grayscale()`   | Removes color             | `grayscale(100%)`               |
| `sepia()`       | Creates sepia effect      | `sepia(100%)`                   |
| `saturate()`    | Changes color intensity   | `saturate(200%)`                |
| `hue-rotate()`  | Rotates colors            | `hue-rotate(90deg)`             |
| `invert()`      | Inverts colors            | `invert(100%)`                  |
| `opacity()`     | Changes transparency      | `opacity(50%)`                  |
| `drop-shadow()` | Adds a shape-based shadow | `drop-shadow(5px 5px 5px gray)` |

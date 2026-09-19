# Images

CSS provides several properties for controlling how images are displayed and how they look. With CSS, we can:

- Control an image's **size**
- Make images **responsive**
- Fit images inside containers
- Crop images when necessary
- Create rounded or circular images
- Apply visual **filters**
- Combine multiple image effects

---

## Images in CSS

Images are usually added to HTML using the `<img>` element. CSS can then control how that image is displayed.

### Image Width and Height

The `width` and `height` properties control the dimensions of an image.

```css
img {
  width: 400px;
  height: 300px;
}
```

However, setting both values independently can distort an image if the aspect ratio is different. If the original image is square, it may appear stretched. A common approach is to set only the width:

```css
img {
  width: 100%;
  height: auto;
}
```

This allows the height to adjust automatically according to the image's original aspect ratio.

### Responsive Images

A responsive image should adapt to the size of its container or screen. A common pattern is:

```css
img {
  max-width: 100%;
  height: auto;
}
```

`max-width: 100%` means the image should not become wider than its container.

`height: auto` maintains the image's aspect ratio.

### `object-fit`

The `object-fit` property controls how replaced elements such as images or videos fit inside their assigned width and height.

The main values are:

| Value        | Meaning                                                                 |
| ------------ | ----------------------------------------------------------------------- |
| `fill`       | Stretches the image to fill the box                                     |
| `contain`    | Shows the entire image inside the box                                   |
| `cover`      | Fills the box while maintaining aspect ratio; some parts may be cropped |
| `none`       | Keeps the original size                                                 |
| `scale-down` | Uses the smaller of `none` or `contain`                                 |

### `object-position`

When an image is cropped using `object-fit: cover`, `object-position` controls **which part of the image stays visible**.

```css
img {
  width: 300px;
  height: 200px;
  object-fit: cover;
  object-position: center;
}
```

Common values:

```css
object-position: center;
object-position: top;
object-position: bottom;
object-position: left;
object-position: right;
```

We can also use percentages or lengths:

```css
object-position: 50% 20%;
```

### Image Borders

Images can be styled like other HTML elements.

```css
img {
  border: 3px solid black;
}
```

We can also use `border-radius`.

```css
img {
  border-radius: 10px;
}
```

### Image Opacity

The `opacity` property controls the transparency of an image. Values range from:

```text
1   → fully visible
0.5 → partially transparent
0   → completely transparent
```

### Hover effect

```css
img {
  opacity: 1;
}

img:hover {
  opacity: 0.7;
}
```

This can create a simple image interaction.

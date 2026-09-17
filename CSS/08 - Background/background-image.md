# Background Image

The `background-image` property places an **image behind the content of an element**.

Syntax:

```css
selector {
  background-image: url("image.jpg");
}
```

Example:

```css
.hero {
  background-image: url("hero.jpg");
}
```

The image becomes the background of the `.hero` element.

## Using an Image URL

The path inside `url()` tells the browser where to find the image. It can be a relative path or ann absolute URL.

## Background Image vs `<img>`

A background image is different from an HTML `<img>` element.

The HTML image is part of the page's **content**.

```html
<img src="profile.jpg" alt="Profile picture" />
```

The CSS background image is part of the element's **visual styling/background**.

```css
.profile {
  background-image: url("profile.jpg");
}
```

## Multiple Background Images

CSS can also use multiple background images. Separate them with commas.

```css
.hero {
  background-image: url("foreground.png"), url("background.jpg");
}
```

The first image is painted above the second image.

```text
Element
┌─────────────────────────┐
│   foreground.png        │  ← top layer
│                         │
│   background.jpg        │  ← lower layer
└─────────────────────────┘
```

---

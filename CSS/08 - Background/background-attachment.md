# Background Attachment

The `background-attachment` property determines whether a background image **scrolls with the element/page or stays fixed relative to the viewport**.

Syntax:

```css
selector {
  background-attachment: value;
}
```

The commonly used values are:

```text
scroll
fixed
local
```

---

## `scroll`

This is the default behavior. The background moves as the page scrolls.

```css
body {
  background-attachment: scroll;
}
```

## `fixed`

With `fixed`, the background stays fixed relative to the viewport while the page content scrolls.

```css
body {
  background-image: url("background.jpg");
  background-attachment: fixed;
}
```

This can be used to create a **fixed background effect**.

## `local`

`local` makes the background scroll with the element's content.

```css
.box {
  background-attachment: local;
}
```

This is particularly relevant for elements that have their own scrolling content.

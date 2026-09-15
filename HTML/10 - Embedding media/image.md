# Images

Images are one of the most common types of media on the web.

```html
<img src="cat.jpg" alt="A sleeping cat" />
```

## `<img>` Attributes

1. `src` - Specifies the image resource.
2. `alt` - Provides alternative text for the image. If the image cannot be seen, the alternative text communicates its meaning.

```html
<img src="cat.jpg" alt="A sleeping cat" />
```

---

### Decorative Images

Not every image carries meaningful information. An empty `alt` tells assistive technologies that the image is decorative and can be skipped.

For a purely decorative image:

```html
<img src="decorative-line.svg" alt="" />
```

---

### Responsive Images

Modern websites often need different image sizes depending on:

- screen size
- device resolution
- layout
- network conditions

HTML provides tools such as:

- `srcset`
- `sizes`
- `<picture>`

Example:

```html
<img
  src="small.jpg"
  srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
  sizes="(max-width: 600px) 480px, 800px"
  alt="Mountain landscape"
/>
```

This gives the browser information about available image resources.

The browser can then select an appropriate image.

---

## `<picture>`

`<picture>` provides more control over which image resource is used.

Example:

```html
<picture>
  <source media="(max-width: 600px)" srcset="mobile.jpg" />

  <source media="(min-width: 601px)" srcset="desktop.jpg" />

  <img src="desktop.jpg" alt="Mountain landscape" />
</picture>
```

Mental model:

```text
<picture>
     │
     ├── Mobile?  → mobile.jpg
     │
     ├── Desktop? → desktop.jpg
     │
     └── <img>    → fallback
```

---

## `<img>` vs `<figure>`

### `<img>`

Use `<img>` when you simply need to embed an image. The image itself is the content.

```html
<img src="profile.jpg" alt="Portrait of Jane" />
```

### `<figure>`

`<figure>` represents **self-contained content** that can be moved away from the surrounding content without losing its meaning. It can contain:

- an image
- a diagram
- a chart
- code
- an illustration
- other content

Example:

```html
<figure>
  <img src="sales-chart.png" alt="Sales increased from January to March" />

  <figcaption>Sales growth during the first quarter.</figcaption>
</figure>
```

#### `<figcaption>`

`<figcaption>` provides a caption or explanation for the `<figure>`.

Think:

```text
<img>
   ↓
The actual image

<figcaption>
   ↓
Information about the image
```

| `<img>`                              | `<figure>`                                              |
| ------------------------------------ | ------------------------------------------------------- |
| Embeds an image                      | Represents a self-contained piece of content            |
| Used directly                        | Can contain an `<img>`                                  |
| Does not provide a caption by itself | Can contain `<figcaption>`                              |
| Good for simple images               | Good for images/diagrams/charts with associated content |

# Priority Hints

Modern websites can contain many resources. The browser needs to decide which resources to fetch first.

```text
HTML
 │
 ├── CSS
 ├── JavaScript
 ├── Images
 ├── Fonts
 ├── Videos
 └── Other resources
```

> Priority hints allow developers to communicate which resources are more or less important.

---

## `fetchpriority`

It can be used with certain resource-fetching elements, including images.

Example:

```html
<img src="hero.jpg" alt="Our main product" fetchpriority="high" />
```

The values are:

```text
high
low
auto
```

---

## Priority Hints vs Lazy Loading

These concepts are related but **not the same**.

`loading="lazy"` - Tells the browser that the resource can be deferred until it is needed/near the viewport.

```html
<img src="photo.jpg" alt="Landscape" loading="lazy" />
```

`fetchpriority` - Communicates the relative importance of fetching a resource.

```html
<img src="hero.jpg" alt="Hero image" fetchpriority="high" />
```

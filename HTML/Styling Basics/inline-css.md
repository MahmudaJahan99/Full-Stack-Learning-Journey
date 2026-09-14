# Inline CSS

**Inline CSS** is CSS written directly inside an HTML element using the `style` attribute.

Syntax:

```html
<element style="property: value;"></element>
```

Example:

```html
<h1 style="color: blue;">Hello World</h1>
```

Here:

```text
<h1
 │
 └── style="color: blue;"
              │
              ├── property → color
              └── value    → blue
```

The CSS is written directly on the element.

## Multiple Properties

Multiple CSS declarations can be written inside the same `style` attribute.

```html
<h1 style="color: blue; font-size: 40px;">Hello World</h1>
```

Each declaration is separated by a semicolon:

### Advantages of Inline CSS

- Element-specific styling
- Quick to implement
- Easy to locate
- High specificity
- Useful for dynamic styling

### Disadvantages of Inline CSS

- Poor reusability
- HTML becomes cluttered
- Difficult maintenance
- Weak separation of concerns
- Harder to manage at scale

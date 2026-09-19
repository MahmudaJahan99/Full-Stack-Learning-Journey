# CSS Variables

CSS Variables, officially called **CSS Custom Properties**, allow us to store reusable values in CSS and use those values throughout a stylesheet.

> A CSS variable is a **custom property that stores a reusable CSS value**. They are called custom properties because we create the property ourselves. The name of a CSS custom property **must begin with `--`**.

Instead of repeating the same value many times:

```css
button {
  background-color: #6c5ce7;
}

.card {
  border-color: #6c5ce7;
}

h1 {
  color: #6c5ce7;
}
```

we can store the color once:

```css
:root {
  --primary-color: #6c5ce7;
}
```

and reuse it:

```css
button {
  background-color: var(--primary-color);
}

.card {
  border-color: var(--primary-color);
}

h1 {
  color: var(--primary-color);
}
```

## Creating a CSS Variable

The basic syntax is:

```css
--variable-name: value;
```

For example:

```css
:root {
  --primary-color: #6c5ce7;
  --text-color: #222;
  --spacing: 20px;
}
```

Here we created three variables:

```text
--primary-color → #6c5ce7
--text-color    → #222
--spacing       → 20px
```

## Using CSS Variables

CSS variables are accessed using the `var()` function.

```css
var(--variable-name)
```

Example:

```css
:root {
  --primary-color: blue;
}

button {
  background-color: var(--primary-color);
}
```

The browser effectively uses `background-color: blue;`.

## Where Can CSS Variables Be Defined?

CSS variables follow the **CSS cascade and inheritance rules**.

They can be defined on:

- `:root`
- `body`
- a specific element
- a component/container

### Using `:root`

A common place to define global variables is `:root`.

```css
:root {
  --primary-color: #6c5ce7;
  --secondary-color: #00b894;
  --text-color: #222;
}
```

`:root` represents the document's root element. For an HTML document, this is the `<html>` element. Because custom properties are inherited, variables defined on `:root` are generally available throughout the page.

### Local CSS Variables

CSS variables don't have to be global. They can be defined on a specific element.

```css
.card {
  --card-color: lightblue;
}
```

Then elements inside that card can use it:

```css
.card {
  --card-color: lightblue;
}

.card h2 {
  color: var(--card-color);
}
```

### Inheritance

Custom properties are **inherited by default**.

For example:

```css
.parent {
  --text-color: blue;
}

.child {
  color: var(--text-color);
}
```

HTML:

```html
<div class="parent">
  <p class="child">Hello</p>
</div>
```

The child can access the variable because it inherits it from the parent.

---

## Fallback Values

The `var()` function can provide a **fallback value**.

Syntax:

```css
var(--variable, fallback-value)
```

Example:

```css
button {
  background-color: var(--primary-color, blue);
}
```

So if `--primary-color` isn't defined, `blue` is used.

---

# CSS Variables for Themes

CSS variables are particularly useful for themes.

For example, define a light theme:

```css
:root {
  --background-color: white;
  --text-color: #222;
  --primary-color: #6c5ce7;
}
```

Then a dark theme could override those values:

```css
.dark-theme {
  --background-color: #222;
  --text-color: white;
  --primary-color: #a29bfe;
}
```

The components can continue using the same variables:

```css
body {
  background-color: var(--background-color);
  color: var(--text-color);
}

button {
  background-color: var(--primary-color);
}
```

The components don't need to know which theme is active.

```text
              CSS Variables
                    │
          ┌─────────┴─────────┐
          │                   │
     Light Theme          Dark Theme
          │                   │
          ▼                   ▼
     Different values    Different values
          │                   │
          └─────────┬─────────┘
                    ▼
                Components
```

---

## CSS Variables Usefulness

CSS variables make CSS:

- **Reusable**
- **Maintainable**
- **Consistent**
- **Easier to update**
- **Easier to theme**
- **Better suited for design systems**

---

## CSS Variables facts

1. CSS custom properties are case-sensitive.
2. A variable can store many types of CSS values.
3. A child element can define its own value for a variable and override it.
4. CSS variables follow the normal CSS cascade. This makes CSS variables useful for creating **component-specific customization**.

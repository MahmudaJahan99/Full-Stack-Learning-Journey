# Sass

**Sass** is a CSS preprocessor that extends CSS with features that make writing large stylesheets easier. Browsers ultimately use CSS, so Sass needs to be processed into CSS before it can be used by the browser.

```text
Sass code
    ↓
Sass compiler
    ↓
CSS
    ↓
Browser
```

Sass has two syntax styles **SCSS** and **Indented Sass**.

SCSS is more commonly encountered in modern projects. SCSS looks very similar to normal CSS:

```scss
$primary-color: blue;

button {
  background-color: $primary-color;
}
```

The browser does not directly understand the `$primary-color` syntax. Sass processes it into CSS:

```css
button {
  background-color: blue;
}
```

## Sass Variables

Sass provides variables using `$`.

```scss
$primary-color: #6c5ce7;
$spacing: 20px;

.card {
  padding: $spacing;
  border-color: $primary-color;
}
```

This is similar in purpose to CSS Variables, but they work differently.

> Sass variable - A Sass variable is resolved during the Sass build process.

```scss
$primary-color: blue;
```

> CSS variable - A CSS custom property remains available in the resulting CSS and can be changed at runtime.

```css
:root {
  --primary-color: blue;
}
```

## Sass Nesting

Sass allows nested rules.

Instead of:

```css
.card {
  background: white;
}

.card h2 {
  color: blue;
}

.card p {
  color: gray;
}
```

SCSS can be written as:

```scss
.card {
  background: white;

  h2 {
    color: blue;
  }

  p {
    color: gray;
  }
}
```

## Sass Mixins

A **mixin** is a reusable group of styles.

Example:

```scss
@mixin center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Use it:

```scss
.hero {
  @include center;
}
```

## Sass Functions

Sass also provides functions for manipulating values. Sass also provides built-in functions for working with colors, lists, maps, strings, and other values.

For example, Sass can perform calculations:

```scss
$base-size: 20px;

.card {
  padding: $base-size * 2;
}
```

Sass evaluates the expression during compilation.

## Sass Partials and Modules

Large Sass projects can be split into multiple files.

For example:

```text
scss/
│
├── _variables.scss
├── _buttons.scss
├── _cards.scss
├── _layout.scss
└── main.scss
```

The files can be organized into logical pieces.

Modern Sass uses the module system with `@use` and `@forward`. This helps organize larger Sass projects.

Example:

```scss
@use "variables";
@use "buttons";
```

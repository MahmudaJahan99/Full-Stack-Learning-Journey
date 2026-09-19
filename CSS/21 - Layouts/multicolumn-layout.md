# Multicolumn Layout

CSS Multicolumn Layout allows content to flow through **multiple columns**, similar to a newspaper or magazine.

we can create:

```text
Column 1        Column 2        Column 3
────────        ────────        ────────
Text            Text            Text
Text            Text            Text
Text            Text            Text
Text            Text            Text
```

## `column-count`

The `column-count` property specifies the number of columns.

Example:

```html
<article class="article">
  <p>Lorem ipsum dolor sit amet...</p>

  <p>More content goes here...</p>
</article>
```

```css
.article {
  column-count: 3;
}
```

The content will automatically flow across three columns.

## `column-width`

Instead of specifying the number of columns, we can specify a preferred column width.

```css
.article {
  column-width: 250px;
}
```

The browser determines how many columns can fit. This can be useful for responsive layouts.

## `columns` Shorthand

`columns` can combine column-related settings.

```css
.article {
  columns: 3 250px;
}
```

This provides a preferred number of columns and column width.

## Column Gap

The `column-gap` property controls the space between columns.

Conceptually:

```text
Column 1       gap       Column 2
────────                  ────────
Text                      Text
Text                      Text
Text                      Text
```

## Column Rule

We can add a line between columns using `column-rule`. `column-rule` works similarly to a border between columns.

```css
.article {
  column-count: 3;
  column-rule: 1px solid gray;
}
```

The result is conceptually:

```text
Column 1       │       Column 2
────────       │       ────────
Text           │       Text
Text           │       Text
```

## Column Span

An element can span across all columns using `column-span`.

```css
h2 {
  column-span: all;
}
```

Example:

```text
        Article Heading
────────────────────────────────
Column 1       Column 2       Column 3
────────       ────────       ────────
Text           Text           Text
Text           Text           Text
```

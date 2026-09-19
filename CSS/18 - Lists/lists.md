# CSS — Lists

HTML provides different types of lists for organizing related items. CSS allows us to control how those lists **look and behave**.

For example:

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

CSS can control:

- List markers
- Numbering style
- Marker position
- List indentation
- List item spacing
- Background and borders
- Horizontal navigation lists
- Custom list designs

## Types of HTML Lists

HTML commonly provides three types of lists. CSS can style all of these differently.

1. Unordered list
2. Ordered list
3. Description list

---

### `list-style-type`

The `list-style-type` property controls the **type of marker** displayed next to list items. Common values include:

```css
list-style-type: disc;
list-style-type: circle;
list-style-type: square;
list-style-type: none;
```

| Value    | Marker    |
| -------- | --------- |
| `disc`   | ●         |
| `circle` | ○         |
| `square` | ■         |
| `none`   | No marker |

Ordered lists can also have different numbering styles. Common values include:

```css
list-style-type: decimal;
list-style-type: decimal-leading-zero;
list-style-type: lower-alpha;
list-style-type: upper-alpha;
list-style-type: lower-roman;
list-style-type: upper-roman;
list-style-type: lower-latin;
list-style-type: upper-latin;
list-style-type: none;
```

### `list-style-position`

The `list-style-position` property controls where the list marker is positioned relative to the list item's content. There are two main values:

```css
list-style-position: outside;
list-style-position: inside;
```

### `list-style-image`

We can replace the normal marker with an image.

```css
ul {
  list-style-image: url("bullet.png");
}
```

the browser can use the specified image as the marker.

### `list-style`

CSS provides a shorthand property called `list-style`. It can combine `list-style-type`, `list-style-position`, and `list-style-image`

Example:

```css
ul {
  list-style: square inside;
}
```

### List Item Styling

The `<li>` element represents an individual list item. We can style it like any other element.

```css
li {
  margin-bottom: 10px;
}
```

This creates space between the items.

### Padding

Browsers normally apply some default padding to lists. We can change it or remove it.

This is especially useful when creating custom list designs.

### Removing Default List Styling

A common pattern for navigation menus is:

```css
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
```

This removes the browser's default marker, padding, and margin.

### ::marker

Modern CSS also allows more customized markers. The `::marker` pseudo-element can style the list marker.

Example:

```css
li::marker {
  font-size: 20px;
  color: red;
}
```

#### `::marker` vs `list-style-type`

`list-style-type` - Controls **what kind of marker** is used:
`::marker` - Allows to style the marker:

### `list-style` Shorthand

Instead of:

```css
ul {
  list-style-type: square;
  list-style-position: inside;
}
```

we can write:

```css
ul {
  list-style: square inside;
}
```

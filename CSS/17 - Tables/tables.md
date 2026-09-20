# CSS — Tables

HTML provides the **structure** of a table, while CSS controls how that table **looks and behaves visually**.

For example:

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>City</th>
  </tr>

  <tr>
    <td>Jane</td>
    <td>26</td>
    <td>Dhaka</td>
  </tr>
</table>
```

CSS can be used to control:

- Table borders
- Cell spacing
- Cell padding
- Text alignment
- Table width
- Column width
- Row height
- Background colors
- Borders between cells
- Alternating rows
- Hover effects

---

## Basic Table Styling

A simple table can be styled with:

```css
table {
  border: 1px solid black;
}

th,
td {
  border: 1px solid black;
}
```

This creates borders around the table and its cells.

```text
┌───────────┬──────────┬──────────┐
│   Name    │   Age    │   City   │
├───────────┼──────────┼──────────┤
│  Jane     │   26     │  Dhaka   │
└───────────┴──────────┴──────────┘
```

### `border-collapse`

By default, table cells can have separate borders.

```css
table {
  border-collapse: separate;
}
```

We can combine the borders using:

```css
table {
  border-collapse: collapse;
}
```

With `collapse`, adjacent cell borders become a single border. `border-collapse: collapse` is very commonly used for clean-looking tables.

```text
Separate:

┌────────┐ ┌────────┐
│        │ │        │
└────────┘ └────────┘


Collapse:

┌────────┬────────┐
│        │        │
└────────┴────────┘
```

### `border-spacing`

We can control the distance between cell borders using `border-spacing`.

```css
table {
  border-collapse: separate;
  border-spacing: 10px;
}
```

Conceptually:

```text
┌───────┐   ┌───────┐
│ Cell  │   │ Cell  │
└───────┘   └───────┘
        ↑
     spacing
```

We can provide horizontal and vertical spacing:

```css
table {
  border-spacing: 20px 10px;
}
```

```text
20px → horizontal spacing
10px → vertical spacing
```

### `padding` in Table Cells

`padding` creates space **inside a cell**, between the content and the cell border.

```css
th,
td {
  padding: 10px;
}
```

```text
┌──────────────┐
│              │
│     Name     │
│              │
└──────────────┘
```

### Horizontal Alignment

The `text-align` property controls horizontal text alignment.

```css
th,
td {
  text-align: left;
}
```

Possible values include `left`, `center`, and `right`

### Vertical Alignment

The `vertical-align` property controls the vertical position of content inside a table cell.

```css
td {
  vertical-align: middle;
}
```

Possible values include `top`, `middle`, and `bottom`

---

### Table Width

We can control the width of a table using `width`.

```css
table {
  width: 100%;
}
```

### Column Width

We can control the width of individual columns.

For example:

```css
th:first-child,
td:first-child {
  width: 40%;
}
```

The remaining space can be distributed among the other columns.

### `table-layout`

The `table-layout` property controls how the browser calculates column widths.

Two important values are `auto` and `fixed`

`auto` - is the default behavior. The browser considers the content when determining column widths.

`fixed` - the browser can calculate column widths without relying as heavily on the content of every cell.

### Styling `<th>` and `<td>`

We can style table headers and data cells separately.

```css
th {
  background-color: #333;
  color: white;
  padding: 12px;
}

td {
  padding: 10px;
}
```

### Alternating Table Rows

CSS can create alternating row colors using `:nth-child()`.

```css
tr:nth-child(even) {
  background-color: #f2f2f2;
}
```

This selects every even-numbered row.

```text
Row 1 → normal
Row 2 → shaded
Row 3 → normal
Row 4 → shaded
Row 5 → normal
```

---

### Hover Effect

We can highlight a row when the user moves the mouse over it. This is useful when a table contains many rows.

```css
tr:hover {
  background-color: #f2f2f2;
}
```

### Border on Specific Sides

We don't always have to add a border to every side.

For example:

```css
td {
  border-bottom: 1px solid #ddd;
}
```

This creates horizontal separators between rows.

```text
Name       Age       City
────────────────────────────
Jane       26        Moscow
────────────────────────────
John       25        LA
────────────────────────────
```

We can also use:

```css
border-top
border-right
border-bottom
border-left
```

### Styling the Table Header

The `<th>` element represents a **table header cell**. We can give it a different appearance:

```css
th {
  padding: 12px;
  text-align: left;
  background-color: #333;
  color: white;
}
```

### Empty Cells

Sometimes a table may contain an empty cell. CSS can control how empty cells are displayed using:

```css
empty-cells: show;

/* or */

empty-cells: hide;
```

This property is mainly relevant when table borders are separated.

---

## Responsive Tables

A wide table can overflow on a small screen. Instead of forcing the table itself to become extremely narrow, it is common to place it inside a container that can scroll horizontally.

### HTML

```html
<div class="table-container">
  <table>
    ...
  </table>
</div>
```

### CSS

```css
.table-container {
  overflow-x: auto;
}

table {
  width: 100%;
  min-width: 600px;
}
```

On a small screen:

```text
┌─────────────────────────┐
│ Name | Age | City | ... │ →
└─────────────────────────┘
             horizontal scroll
```

This prevents a wide table from breaking the layout.

---

# Table Properties at a Glance

| Property           | Purpose                                        |
| ------------------ | ---------------------------------------------- |
| `border`           | Adds a border                                  |
| `border-collapse`  | Controls whether adjacent borders are combined |
| `border-spacing`   | Controls space between cell borders            |
| `padding`          | Creates space inside cells                     |
| `text-align`       | Horizontal alignment                           |
| `vertical-align`   | Vertical alignment                             |
| `width`            | Controls table/cell width                      |
| `height`           | Controls height                                |
| `table-layout`     | Controls how column widths are calculated      |
| `empty-cells`      | Controls display of empty cells                |
| `background-color` | Adds background color                          |
| `overflow-x`       | Useful for horizontally scrolling wide tables  |

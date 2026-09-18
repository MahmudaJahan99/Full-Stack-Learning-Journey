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
        <td>Mahmuda</td>
        <td>26</td>
        <td>Dhaka</td>
    </tr>
</table>
```

CSS can be used to control:

* Table borders
* Cell spacing
* Cell padding
* Text alignment
* Table width
* Column width
* Row height
* Background colors
* Borders between cells
* Alternating rows
* Hover effects

---

# 1. Basic Table Styling

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
│  Mahmuda  │   26     │  Dhaka   │
└───────────┴──────────┴──────────┘
```

---

# 2. `border-collapse`

By default, table cells can have separate borders.

```css
table {
    border-collapse: separate;
}
```

You can combine the borders using:

```css
table {
    border-collapse: collapse;
}
```

### Example

```css
table {
    border-collapse: collapse;
}

th,
td {
    border: 1px solid black;
}
```

With `collapse`, adjacent cell borders become a single border.

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

`border-collapse: collapse` is very commonly used for clean-looking tables.

---

# 3. `border-spacing`

When using:

```css
border-collapse: separate;
```

you can control the distance between cell borders using:

```css
border-spacing: 10px;
```

Example:

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

### Two values

You can provide horizontal and vertical spacing:

```css
table {
    border-spacing: 20px 10px;
}
```

Meaning:

```text
20px → horizontal spacing
10px → vertical spacing
```

---

# 4. `padding` in Table Cells

`padding` creates space **inside a cell**, between the content and the cell border.

```css
th,
td {
    padding: 10px;
}
```

Without padding:

```text
┌──────────┐
│Name      │
└──────────┘
```

With padding:

```text
┌──────────────┐
│              │
│    Name      │
│              │
└──────────────┘
```

This makes table content easier to read.

---

# 5. Horizontal Alignment

The `text-align` property controls horizontal text alignment.

```css
th,
td {
    text-align: left;
}
```

Possible values include:

```css
text-align: left;
text-align: center;
text-align: right;
```

Example:

```css
th {
    text-align: center;
}

td {
    text-align: left;
}
```

---

# 6. Vertical Alignment

The `vertical-align` property controls the vertical position of content inside a table cell.

```css
td {
    vertical-align: middle;
}
```

Common values:

```css
vertical-align: top;
vertical-align: middle;
vertical-align: bottom;
```

Example:

```css
td {
    height: 80px;
    vertical-align: middle;
}
```

The content appears vertically centered.

---

# 7. Table Width

You can control the width of a table using `width`.

```css
table {
    width: 100%;
}
```

For example:

```css
table {
    width: 80%;
}
```

Percentage widths are useful when creating responsive layouts.

A common pattern is:

```css
table {
    width: 100%;
}
```

This allows the table to use the available width of its container.

---

# 8. Column Width

You can control the width of individual columns.

For example:

```css
th:first-child,
td:first-child {
    width: 40%;
}
```

Or:

```css
th:nth-child(2),
td:nth-child(2) {
    width: 20%;
}
```

The remaining space can be distributed among the other columns.

---

# 9. `table-layout`

The `table-layout` property controls how the browser calculates column widths.

Two important values are:

```css
table-layout: auto;
table-layout: fixed;
```

### `auto`

This is the default behavior.

```css
table {
    table-layout: auto;
}
```

The browser considers the content when determining column widths.

### `fixed`

```css
table {
    table-layout: fixed;
}
```

The browser can calculate column widths without relying as heavily on the content of every cell.

Example:

```css
table {
    width: 100%;
    table-layout: fixed;
}
```

This can make column widths more predictable.

---

# 10. Styling `<th>` and `<td>`

You can style table headers and data cells separately.

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

Example:

```text
┌────────────┬────────────┬────────────┐
│    NAME    │    AGE     │    CITY    │  ← <th>
├────────────┼────────────┼────────────┤
│   Mahmuda  │     26     │   Dhaka    │  ← <td>
├────────────┼────────────┼────────────┤
│    Sara    │     25     │   Sylhet   │
└────────────┴────────────┴────────────┘
```

---

# 11. Alternating Table Rows

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

You can also style odd rows:

```css
tr:nth-child(odd) {
    background-color: #f9f9f9;
}
```

---

# 12. Hover Effect

You can highlight a row when the user moves the mouse over it.

```css
tr:hover {
    background-color: #f2f2f2;
}
```

Conceptually:

```text
Normal:

┌─────────┬─────────┐
│ Mahmuda │ Dhaka   │
└─────────┴─────────┘


Hover:

┌─────────┬─────────┐
│ Mahmuda │ Dhaka   │  ← highlighted
└─────────┴─────────┘
```

This is useful when a table contains many rows.

---

# 13. Border on Specific Sides

You don't always have to add a border to every side.

For example:

```css
td {
    border-bottom: 1px solid #ddd;
}
```

This creates horizontal separators between rows.

```text
Name       Age       City
─────────────────────────
Mahmuda    26        Dhaka
─────────────────────────
Sara       25        Sylhet
─────────────────────────
```

You can also use:

```css
border-top
border-right
border-bottom
border-left
```

---

# 14. Styling the Table Header

The `<th>` element represents a **table header cell**.

You can give it a different appearance:

```css
th {
    padding: 12px;
    text-align: left;
    background-color: #333;
    color: white;
}
```

Example:

```text
┌───────────────────────────────────┐
│ Name          Age          City    │
├───────────────────────────────────┤
│ Mahmuda       26           Dhaka   │
│ Sara          25           Sylhet  │
└───────────────────────────────────┘
```

The header visually separates the column labels from the data.

---

# 15. Empty Cells

Sometimes a table may contain an empty cell:

```html
<td></td>
```

CSS can control how empty cells are displayed using:

```css
empty-cells: show;
```

or:

```css
empty-cells: hide;
```

This property is mainly relevant when table borders are separated.

---

# 16. Complete Table Example

### HTML

```html
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>City</th>
    </tr>

    <tr>
        <td>Mahmuda</td>
        <td>26</td>
        <td>Dhaka</td>
    </tr>

    <tr>
        <td>Sara</td>
        <td>25</td>
        <td>Sylhet</td>
    </tr>

    <tr>
        <td>Nadia</td>
        <td>27</td>
        <td>Chittagong</td>
    </tr>
</table>
```

### CSS

```css
table {
    width: 100%;
    border-collapse: collapse;
}

th,
td {
    padding: 12px;
    border-bottom: 1px solid #ddd;
    text-align: left;
}

th {
    background-color: #333;
    color: white;
}

tr:nth-child(even) {
    background-color: #f5f5f5;
}

tr:hover {
    background-color: #eee;
}
```

---

# 17. Responsive Tables

A wide table can overflow on a small screen.

Instead of forcing the table itself to become extremely narrow, it is common to place it inside a container that can scroll horizontally.

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

# 18. Important Table Selectors

CSS selectors can target different parts of a table.

```css
table { }
tr { }
th { }
td { }
```

You can also use pseudo-classes:

```css
tr:hover { }

tr:nth-child(even) { }

tr:nth-child(odd) { }
```

And combinators:

```css
table > tbody > tr { }
```

or:

```css
th,
td { }
```

---

# 19. Table Properties at a Glance

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

---

# 20. `border-collapse` vs `border-spacing`

These two properties are easy to confuse.

### `border-collapse`

Controls whether cell borders are combined.

```css
table {
    border-collapse: collapse;
}
```

### `border-spacing`

Controls the space between separate cell borders.

```css
table {
    border-collapse: separate;
    border-spacing: 10px;
}
```

Think:

```text
border-collapse
      ↓
"Should borders join?"


border-spacing
      ↓
"How much space between borders?"
```

---

# 21. Table Styling Mental Model

Think about a table from **outside → inside**:

```text
                    TABLE
                      │
          ┌───────────┴───────────┐
          │                       │
       Width                  Layout
          │                       │
          └───────────┬───────────┘
                      │
                   Borders
                      │
                 ┌────┴────┐
                 │         │
               Rows      Cells
                           │
                    ┌──────┴──────┐
                    │             │
                 Padding       Content
                    │
             Alignment / Color
```

---

# Quick Summary

* CSS is used to **style HTML tables**.
* `border` adds borders around tables and cells.
* `border-collapse: collapse` combines adjacent cell borders.
* `border-spacing` controls space between separate cell borders.
* `padding` creates space **inside** table cells.
* `text-align` controls horizontal alignment.
* `vertical-align` controls vertical alignment.
* `width` controls the table or column width.
* `table-layout` controls how column widths are calculated.
* `:nth-child()` can create alternating row styles.
* `:hover` can highlight rows.
* `overflow-x: auto` can make wide tables scroll horizontally on small screens.
* `<th>` is used for header cells and `<td>` for data cells.

### One-line memory trick

```text
Table styling = Borders + Spacing + Alignment + Sizing + Appearance
```

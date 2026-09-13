# HTML — Table Tag

Tables are used in HTML to represent **structured tabular data** — information arranged into **rows and columns**.

Examples of data that naturally belongs in a table:

- Student grades
- Product prices
- Employee information
- Monthly sales
- Exam schedules
- Invoices
- Comparison data

---

## What is an HTML Table?

An HTML table is a collection of:

- **Rows**
- **Columns**
- **Cells**
- **Headers**
- **Data**

A simple table looks like this:

```text
┌────────────┬──────────┬─────────┐
│ Name       │ Age      │ Country │
├────────────┼──────────┼─────────┤
│ Jane       │ 27       │ BD      │
├────────────┼──────────┼─────────┤
│ Sara       │ 25       │ USA     │
└────────────┴──────────┴─────────┘
```

In HTML, the main table element is **`<table>`**. However, `<table>` itself doesn't create meaningful rows or cells. We use other elements inside it.

A basic HTML table usually looks like:

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>Country</th>
  </tr>

  <tr>
    <td>Jane</td>
    <td>27</td>
    <td>Bangladesh</td>
  </tr>

  <tr>
    <td>Sara</td>
    <td>25</td>
    <td>USA</td>
  </tr>
</table>
```

The structure can be visualized as:

```text
<table>
│
├── <tr>  ← Row
│   ├── <th>  ← Header cell
│   ├── <th>
│   └── <th>
│
├── <tr>  ← Row
│   ├── <td>  ← Data cell
│   ├── <td>
│   └── <td>
│
└── <tr>  ← Row
    ├── <td>
    ├── <td>
    └── <td>
```

---

### `<table>`

The `<table>` element represents the **entire table**. Everything belonging to the table goes inside it. `<table>` is the **container** for all the tabular information.

Example:

```html
<table>
  <tr>
    <td>Apple</td>
    <td>$2</td>
  </tr>
</table>
```

---

### `<tr>` — Table Row

`<tr>` means **Table Row**. It represents one horizontal row in the table.

Example:

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>

  <tr>
    <td>Jane</td>
    <td>27</td>
  </tr>
</table>
```

Visual representation:

```text
<tr>
 ↓
┌──────────┬─────────┐
│ Name     │ Age     │
└──────────┴─────────┘

<tr>
 ↓
┌──────────┬─────────┐
│ Jane  │ 27      │
└──────────┴─────────┘
```

Every row is represented by a `<tr>`.

---

### `<th>` — Table Header Cell

`<th>` means **Table Header**. It represents a cell containing a heading for a column or row.

Example:

```html
<tr>
  <th>Name</th>
  <th>Age</th>
  <th>Country</th>
</tr>
```

This tells the browser that:

```text
Name     → heading
Age      → heading
Country  → heading
```

> Use `<th>` instead of `<td>` because `<th>` communicates the **meaning** of the content. This is particularly important for **accessibility**.

---

### `<td>` — Table Data Cell

`<td>` means **Table Data**. It represents an ordinary data cell.

Example:

```html
<tr>
  <th>Name</th>
  <th>Age</th>
</tr>

<tr>
  <td>Jane</td>
  <td>27</td>
</tr>
```

---

## The Four Basic Table Elements

| Element   | Meaning      | Purpose                   |
| --------- | ------------ | ------------------------- |
| `<table>` | Table        | Contains the entire table |
| `<tr>`    | Table Row    | Creates a row             |
| `<th>`    | Table Header | Creates a header cell     |
| `<td>`    | Table Data   | Creates a data cell       |

---

## Table Sections

For larger and more organized tables, HTML provides:

- `<thead>` — table header section
- `<tbody>` — table body section
- `<tfoot>` — table footer section

Example:

```html
<table>
  <thead>
    <tr>
      <th>Product</th>
      <th>Price</th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>T-Shirt</td>
      <td>$20</td>
    </tr>

    <tr>
      <td>Jeans</td>
      <td>$40</td>
    </tr>
  </tbody>

  <tfoot>
    <tr>
      <td>Total</td>
      <td>$60</td>
    </tr>
  </tfoot>
</table>
```

The structure becomes:

```text
<table>
│
├── <thead>
│   └── <tr>
│       ├── <th>
│       └── <th>
│
├── <tbody>
│   ├── <tr>
│   │   ├── <td>
│   │   └── <td>
│   │
│   └── <tr>
│       ├── <td>
│       └── <td>
│
└── <tfoot>
    └── <tr>
        ├── <td>
        └── <td>
```

They make the table's structure clearer. They are especially useful for:

- accessibility
- large tables
- CSS styling
- JavaScript manipulation
- understanding the table structure

---

## `<caption>` — Table Title

A table can have a caption using `<caption>`. The caption describes what the table represents. It is the **title of the table**.

```html
<table>
  <caption>
    Student Results
  </caption>

  <tr>
    <th>Name</th>
    <th>Score</th>
  </tr>

  <tr>
    <td>Jane</td>
    <td>95</td>
  </tr>
</table>
```

Output:

```text
          Student Results
        ───────────────────
        Name       Score
        Jane     95
```

---

## `colspan`

Sometimes one cell needs to cover multiple columns. For this we use `colspan`

Example:

```html
<table>
  <tr>
    <th colspan="3">Student Information</th>
  </tr>

  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>Grade</th>
  </tr>

  <tr>
    <td>Jane</td>
    <td>27</td>
    <td>A</td>
  </tr>
</table>
```

Visual idea:

```text
┌─────────────────────────────────┐
│       Student Information       │
├──────────────┬────────┬─────────┤
│ Name         │ Age    │ Grade   │
├──────────────┼────────┼─────────┤
│ Jane      │ 27     │ A       │
└──────────────┴────────┴─────────┘
```

---

## `rowspan`

`rowspan` allows a cell to cover multiple rows.

```html
<table>
  <tr>
    <th>Name</th>
    <th>Subject</th>
  </tr>

  <tr>
    <td rowspan="2">Jane</td>
    <td>HTML</td>
  </tr>

  <tr>
    <td>CSS</td>
  </tr>
</table>
```

Visual idea:

```text
┌──────────┬──────────┐
│ Name     │ Subject  │
├──────────┼──────────┤
│          │ HTML     │
│ Jane  ├──────────┤
│          │ CSS      │
└──────────┴──────────┘
```

---

## `scope` — Connecting Headers to Data

For accessible tables, `<th>` can use the `scope` attribute. This helps assistive technologies understand which headings are associated with which data.

Example:

```html
<table>
  <tr>
    <th scope="col">Name</th>
    <th scope="col">Age</th>
    <th scope="col">Country</th>
  </tr>

  <tr>
    <th scope="row">Jane</th>
    <td>27</td>
    <td>Bangladesh</td>
  </tr>
</table>
```

For simple tables, `scope="col"` is often a good habit.

---

# Quick Reference

| Element / Attribute | Purpose                            |
| ------------------- | ---------------------------------- |
| `<table>`           | Creates the table                  |
| `<caption>`         | Gives the table a title            |
| `<tr>`              | Creates a row                      |
| `<th>`              | Creates a header cell              |
| `<td>`              | Creates a data cell                |
| `<thead>`           | Groups header rows                 |
| `<tbody>`           | Groups body rows                   |
| `<tfoot>`           | Groups footer/summary rows         |
| `colspan`           | Makes a cell span multiple columns |
| `rowspan`           | Makes a cell span multiple rows    |
| `scope`             | Defines what a header applies to   |

# Headings — `<h1>` to `<h6>`

HTML provides six levels of headings:

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```

The levels range from **most important (`h1`) to least important (`h6`)**.

## Visual hierarchy

```text
<h1> Main Heading
  │
  ├── <h2> Section
  │      │
  │      ├── <h3> Subsection
  │      │      │
  │      │      └── <h4> Smaller subsection
  │      │
  │      └── <h3> Another subsection
  │
  └── <h2> Another Section
```

Headings are not simply different font sizes. They create a **document hierarchy**.

Think of them like the table of contents of a book:

```text
H1 → Book / Main Topic
 │
 ├── H2 → Chapter
 │    │
 │    ├── H3 → Section
 │    │
 │    └── H3 → Section
 │
 └── H2 → Chapter
```

---

### `<h1>`

`<h1>` represents the main heading of a page or major document section. Generally, a page should have a clear primary heading.

```html
<h1>My Full Stack Learning Journey</h1>
```

---

### `<h2>`

`<h2>` represents a major section under the main `<h1>` heading. A page can have multiple `<h2>` headings when it contains several major sections.

```html
<h1>My Full Stack Learning Journey</h1>

<h2>HTML</h2>

<h2>CSS</h2>

<h2>JavaScript</h2>
```

---

### `<h3>`

`<h3>` represents a subsection inside an `<h2>` section.

```html
<h1>My Full Stack Learning Journey</h1>

<h2>Frontend Development</h2>

<h3>HTML</h3>

<h3>CSS</h3>

<h3>JavaScript</h3>
```

Here:

```text
H1 → My Full Stack Learning Journey
 │
 └── H2 → Frontend Development
       │
       ├── H3 → HTML
       ├── H3 → CSS
       └── H3 → JavaScript
```

The `<h3>` headings make the structure of the section clearer.

---

### `<h4>`

`<h4>` represents a subsection inside an `<h3>` section. It is useful when content needs another level of organization.

```html
<h1>Web Development</h1>

<h2>JavaScript</h2>

<h3>Functions</h3>

<h4>Function Declaration</h4>

<h4>Function Expression</h4>

<h4>Arrow Function</h4>
```

The hierarchy is:

```text
H1 → Web Development
 │
 └── H2 → JavaScript
       │
       └── H3 → Functions
             │
             ├── H4 → Function Declaration
             ├── H4 → Function Expression
             └── H4 → Arrow Function
```

`<h4>` should normally describe content that belongs to the preceding `<h3>` section.

---

### `<h5>`

`<h5>` represents a subsection inside an `<h4>` section. It is less commonly needed, but it can be useful for deeply structured documents.

---

### `<h6>`

`<h6>` is the lowest heading level available in HTML. `<h6>` is the **least important heading level** in HTML. It is generally used only when a document has a very deep structure.

---

## Complete Heading Hierarchy

All six heading levels can be visualized like this:

```text
<h1> Main Topic
 │
 ├── <h2> Major Section
 │    │
 │    ├── <h3> Subsection
 │    │    │
 │    │    ├── <h4> Smaller Subsection
 │    │    │    │
 │    │    │    ├── <h5> Detailed Subsection
 │    │    │    │    │
 │    │    │    │    └── <h6> Very Detailed Subsection
 │    │    │    │
 │    │    │    └── <h5> Another Detailed Subsection
 │    │    │
 │    │    └── <h4> Another Smaller Subsection
 │    │
 │    └── <h3> Another Subsection
 │
 └── <h2> Another Major Section
```

---

## Headings and Accessibility

Proper heading structure is also important for accessibility. Screen readers can use headings to help users understand and navigate a page.

A well-structured document might look like gives both users and assistive technologies a meaningful outline of the content.

---

### A simple rule to remember

```text
<h1> → Main topic
<h2> → Major section
<h3> → Subsection
<h4> → Sub-subsection
<h5> → Detailed subsection
<h6> → Most detailed subsection
```

**Don't skip heading levels just for styling.** Ideally, the heading structure should reflect the logical organization of your content.

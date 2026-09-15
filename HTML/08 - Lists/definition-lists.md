# Definition Lists

A **definition list** is used to represent a collection of terms and their corresponding descriptions. Unlike `<ol>` and `<ul>`, it doesn't use `<li>`.
It can represent **a group of terms and their associated information**.

Instead, it uses three elements:

```text
<dl>
 │
 ├── <dt> → Definition Term
 │
 └── <dd> → Definition Description
```

Basic syntax

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language.</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets.</dd>

  <dt>JavaScript</dt>
  <dd>
    A programming language used to add behavior and interactivity to web pages.
  </dd>
</dl>
```

Conceptually:

```text
HTML
    HyperText Markup Language.

CSS
    Cascading Style Sheets.

JavaScript
    A programming language used to add behavior...
```

## `<dl>` — Description List, `<dt>` — Description Term, and `<dd>` — Description

`<dl>` represents the **entire description list**.

`<dt>` represents the **term or name** being described.

`<dd>` provides the description, definition, or associated information for the term.

```html
<dl>
  <dt>What is HTML?</dt>
  <dd>HTML provides the structure of web pages.</dd>

  <dt>What is CSS?</dt>
  <dd>CSS controls the presentation of web pages.</dd>
</dl>
```

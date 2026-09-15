# Ordered Lists

An **ordered list** is used when the order of the items matters.

The HTML element for an ordered list is `<ol></ol>`. Each item inside the list is represented using `<li></li>`.

Basic syntax:

```html
<ol>
  <li>Wake up</li>
  <li>Study HTML</li>
  <li>Practice coding</li>
</ol>
```

The browser displays:

```text
1. Wake up
2. Study HTML
3. Practice coding
```

> `<ol>` is the **container** and `<li>` is the **individual list item**.

Use an ordered list when the **sequence or ranking is meaningful**. Switching the order could change the result.

For example, a recipe:

```html
<ol>
  <li>Prepare the ingredients.</li>
  <li>Heat the pan.</li>
  <li>Add the vegetables.</li>
  <li>Cook for 10 minutes.</li>
</ol>
```

## `<ol>` vs `<li>`

These two elements have different responsibilities. `<ol>` defines the **type of list**. `<li>` defines an **individual list item**.

```text
<ol>
 │
 │  "This is an ordered list."
 │
 ├── <li>
 │      "This is one item."
 │
 ├── <li>
 │      "This is another item."
 │
 └── <li>
        "This is another item."
```

---

## Changing the Numbering

Ordered lists can use different numbering systems.

Common `type` values include:

| `type` | Result     |
| ------ | ---------- |
| `1`    | 1, 2, 3    |
| `A`    | A, B, C    |
| `a`    | a, b, c    |
| `I`    | I, II, III |
| `i`    | i, ii, iii |

Example:

```html
<ol type="I">
  <li>Introduction</li>
  <li>HTML</li>
  <li>CSS</li>
</ol>
```

Result:

```text
I. Introduction
II. HTML
III. CSS
```

> In modern development, CSS is generally preferred when you want to customize the visual appearance of list markers.

---

## Starting an Ordered List at a Different Number

The `start` attribute allows an ordered list to begin at a particular number.

```html
<ol start="5">
  <li>Fifth item</li>
  <li>Sixth item</li>
  <li>Seventh item</li>
</ol>
```

Result:

```text
5. Fifth item
6. Sixth item
7. Seventh item
```

This can be useful when continuing a list from a previous section.

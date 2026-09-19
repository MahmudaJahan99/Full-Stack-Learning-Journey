# CSS — Pseudo-Classes and Pseudo-Elements

**pseudo-classes** and **pseudo-elements** are useful when we want to style:

- An element when a **specific condition or state** occurs
- A **specific part** of an element
- Something that is not explicitly written as a separate HTML element

---

## Pseudo-Classes

A **pseudo-class** is a keyword added to a selector to style an element based on its **state, position, or condition**.

Syntax:

```css
selector:pseudo-class {
  property: value;
}
```

Pseudo-classes allow CSS to react to different situations without JavaScript.

For example:

```css
a:hover {
  color: red;
}
```

The link changes color when the user hovers over it.

Common uses include:

- Hover effects
- Focus styles
- Visited links
- Form validation states
- Selecting elements based on their position
- Styling the first or last element
- Styling elements based on their relationship to siblings

### Common Pseudo-Classes

| Pseudo-class     | Purpose                                     |
| ---------------- | ------------------------------------------- |
| `:hover`         | Element is being hovered                    |
| `:active`        | Element is being activated                  |
| `:focus`         | Element has focus                           |
| `:visited`       | Link has been visited                       |
| `:link`          | Unvisited link                              |
| `:first-child`   | First child of its parent                   |
| `:last-child`    | Last child of its parent                    |
| `:nth-child()`   | Selects children based on position          |
| `:first-of-type` | First element of its type                   |
| `:last-of-type`  | Last element of its type                    |
| `:nth-of-type()` | Selects elements based on type and position |
| `:not()`         | Excludes matching elements                  |
| `:is()`          | Matches any selector in a group             |
| `:where()`       | Groups selectors with zero specificity      |
| `:checked`       | Checked form control                        |
| `:disabled`      | Disabled form control                       |
| `:enabled`       | Enabled form control                        |
| `:required`      | Required form control                       |
| `:valid`         | Valid form control                          |
| `:invalid`       | Invalid form control                        |
| `:empty`         | Element has no children                     |

---

## Pseudo-Elements

A **pseudo-element** allows to style a **specific part of an element** or create generated content.

Syntax:

```css
selector::pseudo-element {
  property: value;
}
```

### Common Pseudo-Elements

| Pseudo-element   | Purpose                                               |
| ---------------- | ----------------------------------------------------- |
| `::before`       | Inserts generated content before an element's content |
| `::after`        | Inserts generated content after an element's content  |
| `::first-letter` | Styles the first letter                               |
| `::first-line`   | Styles the first line                                 |
| `::marker`       | Styles list markers                                   |
| `::selection`    | Styles selected/highlighted text                      |
| `::placeholder`  | Styles placeholder text                               |

---

## The `content` Property

`::before` and `::after` commonly use the `content` property.

```css
.box::before {
  content: "Hello";
}
```

Without `content`, these pseudo-elements generally won't display generated content.

We can use:

```css
content: "Text";
```

or:

```css
content: "";
```

An empty value is useful when the pseudo-element is being used as a visual shape or decorative element.

---

## Pseudo-Class vs Pseudo-Element

| Feature    | Pseudo-Class                  | Pseudo-Element                          |
| ---------- | ----------------------------- | --------------------------------------- |
| Represents | State, condition, or position | Part of an element or generated content |
| Syntax     | `:`                           | `::`                                    |
| Example    | `:hover`                      | `::before`                              |
| Example    | `:focus`                      | `::after`                               |
| Example    | `:nth-child()`                | `::first-letter`                        |
| Example    | `:checked`                    | `::marker`                              |
| Common use | Interaction/state             | Decoration/content styling              |

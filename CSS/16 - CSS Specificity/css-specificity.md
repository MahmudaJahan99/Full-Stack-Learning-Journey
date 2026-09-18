# CSS — Specificity

When multiple CSS rules target the **same element** and set the **same property**, the browser needs to decide which CSS rule should win. This is where **CSS specificity** comes in.

**Specificity** is the set of rules the browser uses to determine **which CSS selector is more specific** when multiple selectors match the same element.

For example:

```html
<p id="intro" class="text">Hello World</p>
```

Suppose we have:

```css
p {
  color: blue;
}

.text {
  color: green;
}

#intro {
  color: red;
}
```

The **ID selector is more specific**, so the text becomes red.
All three selectors match the `<p>`. But the browser gives them different levels of specificity.

```text
p       → Element selector
.text   → Class selector
#intro  → ID selector
```

Without specificity, the browser wouldn't know which rule to apply when multiple rules target the same element. Specificity helps make that decision.

## Specificity Hierarchy

A useful simplified hierarchy is:

```text
                Most specific
                     ↑
                Inline styles
                     │
                     │
                     ID selectors
                     │
                     │
              Class / Attribute
                 / Pseudo-class
                     │
                     │
               Element selectors
              / Pseudo-elements
                     │
                     │
              Universal selector
                     ↓
                Least specific
```

For selectors themselves:

```text
ID
 ↓
Class / Attribute / Pseudo-class
 ↓
Element / Pseudo-element
 ↓
Universal
```

---

### Element Selectors

An element selector has a low specificity level.

Example:

```css
p {
  color: blue;
}
```

### Class Selectors

A class selector is more specific than an element selector.

```css
.text {
  color: green;
}
```

### ID Selectors

An ID selector has higher specificity than a class selector.

```css
#title {
  color: red;
}
```

### Inline Styles

An inline style has an even higher specificity level than IDs in the simplified specificity model. The inline style takes precedence over ordinary author stylesheet selectors.

```html
<p id="intro" style="color: orange;">Hello</p>
```

### Attribute Selectors

Attribute selectors have the same specificity category as classes.

```css
[type="email"] {
  border: 1px solid blue;
}
```

### Pseudo-classes

Pseudo-classes also have the same specificity category as classes.

```css
button:hover {
  background: black;
}
```

### Pseudo-elements

Pseudo-elements belong to the element-level category.

```css
p::first-letter {
  font-size: 40px;
}
```

### Universal Selector

The universal selector has **zero specificity**. It does not add to the specificity calculation.

```css
* {
  box-sizing: border-box;
}
```

### Combining Selectors

Selectors can contain multiple parts. For example:

```css
.card p {
  color: blue;
}
```

### Multiple Classes

Consider:

```css
.card.featured {
  color: blue;
}
```

There are two class selectors and so more specific than one class.

---

## How Specificity is Compared

The browser compares specificity **from left to right**.

Specificity is **not the only thing** involved in deciding which CSS rule wins.

Suppose two selectors have the same specificity:

```css
p {
  color: blue;
}

p {
  color: red;
}
```

Both have:

```text
0,0,0,1
```

The second rule wins because it appears later.

This is called **source order**.

---

## Specificity and the Cascade

Specificity is one part of the larger **CSS cascade**.

A simplified mental model is:

```text
CSS declarations
       │
       ↓
Importance / Origin
       │
       ↓
Specificity
       │
       ↓
Source Order
       │
       ↓
Final applied style
```

So specificity does not work completely independently. The browser considers the broader cascade when deciding which declaration wins.

---

# `!important`

`!important` gives a declaration special priority.

Example:

```css
p {
  color: blue !important;
}

#message {
  color: red;
}
```

Even though `#message` has higher normal specificity, the `!important` declaration has higher priority in the relevant cascade comparison.

---

## A Simple Specificity Table

| Selector        | Specificity |
| --------------- | ----------: |
| `*`             |   `0,0,0,0` |
| `p`             |   `0,0,0,1` |
| `.text`         |   `0,0,1,0` |
| `[type="text"]` |   `0,0,1,0` |
| `:hover`        |   `0,0,1,0` |
| `#title`        |   `0,1,0,0` |
| `.card p`       |   `0,0,1,1` |
| `#app .card`    |   `0,1,1,0` |
| `#app .card p`  |   `0,1,1,1` |

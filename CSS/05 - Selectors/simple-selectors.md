# CSS — Simple Selectors

A **CSS selector** is used to tell CSS **which HTML element(s) should be styled**. The **selector** is the part that chooses the HTML element.

---

## 1. Element Selector

The **element selector** selects HTML elements based on their **tag name**.

Syntax:

```css
element {
  property: value;
}
```

Element selectors are useful when we want to apply the **same basic style to every element of a particular type**.

Example:

```css
p {
  color: blue;
}
```

This applies the color blue to all paragraphs.

---

## 2. Class Selector

The **class selector** selects elements that have a particular `class` attribute. A class selector starts with a **`.` (dot)**.

Syntax:

```css
.class-name {
  property: value;
}
```

A class can be reused. This is one of the most important features of classes.

```html
<h1 class="title">My Website</h1>
<p class="title">Welcome to my website.</p>
```

```css
.title {
  color: purple;
}
```

Both elements receive the style. A class is therefore useful when **multiple elements need the same styling**.

### Multiple Classes

An element can have more than one class.

```html
<button class="button primary">Save</button>
```

```css
.button {
  padding: 10px 20px;
}

.primary {
  background-color: blue;
}
```

The button receives styles from both classes.

---

## 3. ID Selector

The **ID selector** selects an element based on its `id` attribute. An ID selector starts with a **`#` (hash)**.

Syntax:

```css
#id-name {
  property: value;
}
```

HTML:

```html
<h1 id="main-title">Welcome</h1>
```

CSS:

```css
#main-title {
  color: green;
}
```

---

### Class vs ID

| Class                    | ID                                      |
| ------------------------ | --------------------------------------- |
| Starts with `.`          | Starts with `#`                         |
| Can be reused            | Intended to identify one unique element |
| `.card`                  | `#main-card`                            |
| Good for reusable styles | Good for a specific element             |

---

## 4. Universal Selector

The **universal selector** selects **all elements**. It is represented by an asterisk **`*`**

Syntax:

```css
* {
  property: value;
}
```

The universal selector applies the rule to all elements.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

This selects every element and sets its margin to `0`.

The universal selector is often useful for applying a **general rule across the page**. It can also be used in simple CSS resets.

---

# 5. Grouping Selector

Sometimes we want to give the **same styles to multiple different selectors**. Instead of writing separate CSS rules, we can group the selectors using a **comma `,`**.

```css
h1,
h2,
p {
  color: blue;
}
```

One rule applies to all three selectors.

---

## Quick Summary

Selectors are basically used to select elements from HTML for styling.

```text
Element Selector
       │
       ▼
    Selects elements by their tag name

Class Selector
       │
       ▼
    Selects elements by their class

ID Selector
       │
       ▼
    Selects an element by its ID

Universal Selector
       │
       ▼
    Selects all elements

Grouping Selector
       │
       ▼
    Selects multiple selectors and applies the same styles
```

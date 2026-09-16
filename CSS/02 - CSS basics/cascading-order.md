# Cascading Order

> The word **Cascading** in **Cascading Style Sheets** refers to the process browsers use to determine which CSS declarations should apply when multiple rules target the same element.

For example, suppose we have:

```html
<p class="message">Hello World</p>
```

And multiple CSS rules target the paragraph:

```css
p {
  color: blue;
}

.message {
  color: green;
}
```

Both rules match the same element. So which color should the browser use? The CSS cascade determines the answer.

## What Determines Which CSS Rule Wins?

When competing CSS declarations apply to the same element, the browser considers several factors. A useful simplified model is:

```text
1. Origin & importance
          ↓
2. Specificity
          ↓
3. Source order
```

These work together to determine the final style.

---

### 1. `!important`

The `!important` annotation gives a declaration special priority within the cascade.

Example:

```css
p {
  color: blue !important;
}

p {
  color: red;
}
```

The result will be _blue_ because the first declaration is marked `!important`.

However, `!important` should not be used unnecessarily. Excessive use can make CSS difficult to override and maintain. It is better to understand why a rule is losing in the cascade before reaching for `!important`.

---

### 2. Specificity

**Specificity** determines how strongly a selector targets an element.

Example:

```html
<p class="message">Hello</p>
```

```css
p {
  color: blue;
}

.message {
  color: green;
}
```

The class selector has greater specificity than the element selector, so the paragraph becomes _green_.

#### Specificity Hierarchy

A simplified specificity hierarchy is:

```text
Universal selector
        ↓
Element selectors
        ↓
Class / attribute / pseudo-class selectors
        ↓
ID selectors
        ↓
Inline styles
```

Example:

```css
/* Element */
p {
  color: blue;
}

/* Class */
.message {
  color: green;
}

/* ID */
#special {
  color: red;
}
```

HTML:

```html
<p id="special" class="message">Hello World</p>
```

All three selectors match the element. The simplified specificity comparison is:

```text
p
↓
Lower

.message
↓
Higher

#special
↓
Higher still
```

Therefore _`#special`_ wins and the text becomes red.

---

### 3. Source Order

If two declarations have the **same level of specificity**, the rule that appears later in the CSS generally wins.

Example:

```css
p {
  color: blue;
}

p {
  color: red;
}
```

Both selectors are identical. Therefore, the later declaration wins. This is why it is called **source order**.

---

## Inline CSS and the Cascade

Inline CSS also participates in the cascade. The inline style generally takes precedence over the normal stylesheet rule.

```text
External/Internal rule
        ↓
.message → green

Inline style
        ↓
style="color: purple;"
        ↓
Wins
```

Therefore, the paragraph appears purple.

---

### Cascading Order in complex scenario

When multiple CSS declarations compete, the browser evaluates the cascade to determine which declaration applies.

```text
Same property
      |
      ↓
Which declarations apply?
      |
      ↓
Compare cascade priority
      |
      ↓
Compare specificity
      |
      ↓
If still tied → source order
      |
      ↓
Final value
```

> **CSS does not simply apply every rule independently. When rules conflict, the cascade determines which declaration ultimately controls the element.**

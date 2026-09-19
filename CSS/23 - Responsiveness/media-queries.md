# Media Queries

A **media query** allows CSS to apply different styles depending on conditions such as:

- viewport width
- viewport height
- orientation
- device capabilities

The most commonly used condition is **viewport width**.

Basic Syntax:

```css
@media (condition) {
  /* CSS rules */
}
```

## `min-width`

`min-width` applies styles when the viewport is **at least** the specified width.

```css
@media (min-width: 768px) {
  .container {
    width: 80%;
  }
}
```

Meaning:

```text
Viewport width ≥ 768px
        ↓
Apply these styles
```

## `max-width`

`max-width` applies styles when the viewport is **at most** the specified width.

```css
@media (max-width: 768px) {
  .container {
    width: 95%;
  }
}
```

Meaning:

```text
Viewport width ≤ 768px
        ↓
Apply these styles
```

---

## Mobile-First Approach

A common responsive design strategy is **mobile-first design**. The idea is to start with the styles for smaller screens, then add styles for larger screens.

The default layout is designed for smaller screens. This approach often makes responsive layouts easier to manage.

### Common Media Query Breakpoints:

```css
@media (min-width: 480px) {
  /* small screens */
}

@media (min-width: 768px) {
  /* tablets */
}

@media (min-width: 1024px) {
  /* laptops */
}

@media (min-width: 1280px) {
  /* large screens */
}
```

However, these numbers are **not strict rules**. A better approach is to choose breakpoints based on **when the design actually needs to change**.

### Combining Media Query Conditions

Media queries can contain multiple conditions.

```css
@media (min-width: 768px) and (max-width: 1200px) {
  .container {
    padding: 30px;
  }
}
```

This applies when **768px ≤ viewport width ≤ 1200px**

---

## Orientation

Media queries can also detect orientation. The two main values are `portrait` and `landscape`

```css
@media (orientation: landscape) {
  .hero {
    min-height: 80vh;
  }
}
```

And:

```css
@media (orientation: portrait) {
  .hero {
    min-height: 60vh;
  }
}
```

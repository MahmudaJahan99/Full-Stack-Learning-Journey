# Standard Attributes

HTML elements can have **attributes** that provide additional information about the element or change how it behaves.

```text
<a href="https://example.com">
   │       │
   │       └── Attribute value
   │
   └── Attribute name
```

The general syntax is:

```html
<element attribute="value"></element>
```

> Attributes give us a way to **identify, classify, store custom information about, or style HTML elements**.

---

## What Are Attributes?

An attribute is additional information placed inside an HTML element's opening tag.

For example:

```html
<h1 id="main-title" class="heading">My Website</h1>
```

Think of the element as an object and its attributes as additional information attached to it:

```text
                    <h1>
                     │
          ┌──────────┴──────────┐
          │                     │
       id="main-title"      class="heading"
          │                     │
          ▼                     ▼
      Identification         Classification
```

---

## Standard Attributes

HTML provides many standard attributes. Some of the most commonly encountered ones are:

- id
- class
- data-\* attributes
- style

---

## Attributes Can Work Together

These attributes are not mutually exclusive. A single element can have several attributes:

```html
<button
  id="buy-button"
  class="button primary"
  data-product-id="101"
  style="font-size: 18px;"
>
  Buy Now
</button>
```

Each attribute has a different responsibility.

```text
<button>
    │
    ├── id
    │    └── Unique identification
    │
    ├── class
    │    └── Group/category
    │
    ├── data-*
    │    └── Custom information
    │
    └── style
         └── Inline presentation
```

# Nested Lists

A **nested list** is a list placed inside another list. This is useful when information has multiple levels of hierarchy.

For example:

```html
<ul>
  <li>
    Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>

  <li>
    Backend
    <ul>
      <li>Node.js</li>
      <li>Databases</li>
    </ul>
  </li>
</ul>
```

The structure is:

```text
<ul>
 │
 ├── <li> Frontend
 │      │
 │      └── <ul>
 │           ├── <li> HTML
 │           ├── <li> CSS
 │           └── <li> JavaScript
 │
 └── <li> Backend
        │
        └── <ul>
             ├── <li> Node.js
             └── <li> Databases
```

When nesting a list, the nested `<ul>` or `<ol>` should be placed **inside the relevant `<li>`**.

## Nested Ordered Lists

Nested lists don't have to be unordered. We can place an ordered list inside an ordered list:

```html
<ol>
  <li>
    Learn HTML

    <ol>
      <li>Elements</li>
      <li>Attributes</li>
      <li>Forms</li>
    </ol>
  </li>

  <li>
    Learn CSS

    <ol>
      <li>Selectors</li>
      <li>Flexbox</li>
      <li>Grid</li>
    </ol>
  </li>
</ol>
```

Conceptually:

```text
1. Learn HTML
   1. Elements
   2. Attributes
   3. Forms

2. Learn CSS
   1. Selectors
   2. Flexbox
   3. Grid
```

---

## Mixing Ordered and Unordered Lists

For example:

```html
<ol>
  <li>
    Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>

  <li>
    Backend
    <ul>
      <li>Node.js</li>
      <li>Express</li>
    </ul>
  </li>
</ol>
```

Result:

```text
1. Frontend
   • HTML
   • CSS
   • JavaScript

2. Backend
   • Node.js
   • Express
```

This is useful when the **outer relationship has an order**, while the items inside each category do not.

---

## Lists Can Have Multiple Levels

There is no requirement that a nested list only have one additional level.

For example:

```html
<ul>
  <li>
    Frontend

    <ul>
      <li>
        JavaScript

        <ul>
          <li>Variables</li>
          <li>Functions</li>
          <li>Objects</li>
        </ul>
      </li>

      <li>CSS</li>
    </ul>
  </li>
</ul>
```

The hierarchy becomes:

```text
Frontend
│
├── JavaScript
│   │
│   ├── Variables
│   ├── Functions
│   └── Objects
│
└── CSS
```

The HTML should represent the **actual information hierarchy**.

# Semantic Markup

Semantic markup means using HTML elements according to the **meaning and purpose of the content**, rather than choosing elements only for how they look. Semantic markup gives the browser, assistive technologies, search engines, and other developers more information about the structure of the document.

For example, instead of creating a generic `<div>` and calling it a header:

```html
<div class="header">
  <h1>My Website</h1>
</div>
```

we can communicate the actual meaning of that area:

```html
<header>
  <h1>My Website</h1>
</header>
```

---

# Semantic vs Non-Semantic Elements

## Non-semantic elements

Non-semantic elements don't tell us much about the content they contain.

Example:

```html
<div class="header">...</div>

<div class="navigation">...</div>

<div class="main-content">...</div>
```

A developer can understand the purpose from the class names, but the HTML elements themselves don't communicate those meanings.

## Semantic elements

Semantic elements describe their purpose.

Examples:

```html
<header></header>
<nav></nav>
<main></main>
<section></section>
<article></article>
<aside></aside>
<footer></footer>
```

Now the structure itself communicates meaning.

```text
┌───────────────────────────────────────────┐
│                  HEADER                   │
│             Logo + Introduction           │
├───────────────────────────────────────────┤
│                   NAV                     │
│       Home | About | Blog | Contact       │
├───────────────────────────────────────────┤
│                                           │
│                   MAIN                    │
│                                           │
│   ┌─────────────────────┐ ┌────────────┐ │
│   │                     │ │            │ │
│   │      ARTICLE        │ │   ASIDE    │ │
│   │                     │ │            │ │
│   └─────────────────────┘ └────────────┘ │
│                                           │
├───────────────────────────────────────────┤
│                  FOOTER                   │
└───────────────────────────────────────────┘
```

---

## Putting the Layout Elements Together

A simple semantic page might look like this:

```html
<body>
  <header>
    <h1>My Blog</h1>
  </header>

  <nav>
    <a href="/">Home</a>
    <a href="/blog">Blog</a>
    <a href="/about">About</a>
  </nav>

  <main>
    <article>
      <header>
        <h2>Learning Semantic HTML</h2>
      </header>

      <p>Semantic HTML gives meaning to the structure of a webpage.</p>

      <section>
        <h3>Why It Matters</h3>
        <p>
          It improves structure, accessibility, maintainability, and machine
          understanding.
        </p>
      </section>

      <footer>
        <p>Written by Jane Doe</p>
      </footer>
    </article>

    <aside>
      <h2>Related Topics</h2>
      <ul>
        <li>Accessibility</li>
        <li>HTML Forms</li>
        <li>CSS</li>
      </ul>
    </aside>
  </main>

  <footer>
    <p>&copy; 2026 My Blog</p>
  </footer>
</body>
```

The conceptual structure is:

```text
<body>
 │
 ├── <header>
 │
 ├── <nav>
 │
 ├── <main>
 │    │
 │    ├── <article>
 │    │     │
 │    │     ├── <header>
 │    │     ├── content
 │    │     ├── <section>
 │    │     └── <footer>
 │    │
 │    └── <aside>
 │
 └── <footer>
```

---

## Semantic HTML and Accessibility

One of the biggest advantages of semantic HTML is **accessibility**. Assistive technologies such as screen readers can use the semantic structure of a page to help users navigate it.

The class name is meaningful to developers, but it does not create the same native HTML semantics.

---

## Semantic HTML and SEO

Semantic HTML can also help search engines understand the structure and meaning of website content. It gives a clearer document structure than a page built entirely from generic containers.

However, Semantic HTML does **not** magically guarantee better SEO. Semantic HTML is one part of creating a well-structured website.

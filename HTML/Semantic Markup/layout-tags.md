# Layout Tags

These elements help describe the **structure of a webpage**. Instead of creating a page entirely from `<div>` elements, semantic layout elements let us communicate what each area represents. This is a **conceptual structure**, not a rule that every website must follow exactly.

## `<header>` — Introductory Content

`<header>` represents introductory or navigational content for a page or a section. It can contain things such as:

- Logo
- Heading
- Introduction
- Navigation
- Author information

Example:

```html
<header>
  <h1>My Blog</h1>
  <p>Learning web development one step at a time.</p>
</header>
```

A `<header>` doesn't have to represent only the topmost part of the entire webpage. It can also belong to an individual section or article:

## `<nav>` — Navigation

`<nav>` represents a section containing **major navigation links**.

Example:

```html
<nav aria-label="Main navigation">
  <a href="/">Home</a>
  <a href="/about">About</a>
  <a href="/projects">Projects</a>
  <a href="/contact">Contact</a>
</nav>
```

A page may have more than one navigation area.

## `<main>` — Main Content

`<main>` represents the **dominant content of the document**. The main content should not normally contain repeated site-wide content

Example:

```html
<main>
  <h1>Learning HTML</h1>

  <p>HTML provides structure and meaning to web content.</p>
</main>
```

A typical page has one primary `<main>` element.

## `<section>` — Thematic Section

`<section>` represents a **thematic grouping of content**. A section usually has a heading.

Example:

```html
<section>
  <h2>HTML</h2>
  <p>HTML provides the structure of a webpage.</p>
</section>

<section>
  <h2>CSS</h2>
  <p>CSS controls presentation and visual styling.</p>
</section>
```

## `<article>` — Self-Contained Content

`<article>` represents content that is **self-contained** and could potentially be distributed or reused independently.

Common examples:

- Blog posts
- News articles
- Forum posts
- Reviews
- Comments
- Independent pieces of content

Example:

```html
<article>
  <h2>What Is Semantic HTML?</h2>

  <p>
    Semantic HTML means choosing elements based on the meaning of the content.
  </p>
</article>
```

## `<aside>` — Secondary Content

`<aside>` represents content that is **related to, but not part of, the main content**.

Common examples include:

- Sidebars
- Related articles
- Additional information
- Pull quotes
- Glossaries
- Supporting links

Example:

```html
<main>
  <article>
    <h1>What Is HTML?</h1>

    <p>HTML is the standard markup language for creating web pages.</p>
  </article>

  <aside>
    <h2>Related Topics</h2>
    <ul>
      <li>CSS</li>
      <li>JavaScript</li>
      <li>Accessibility</li>
    </ul>
  </aside>
</main>
```

The article is the primary content. The related topics are useful, but secondary.

## `<footer>` — Footer Content

`<footer>` represents footer information for the nearest sectioning content or the entire page. A `<footer>` can also belong to an individual article. It can contain:

- Copyright information
- Author information
- Related links
- Contact information
- Additional navigation

Example:

```html
<footer>
  <p>&copy; 2026 Jane Doe</p>
</footer>
```

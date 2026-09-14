# Quotation and Citation

They don't all represent quotations or citations in the strict sense. Some describe **terms, abbreviations, contact information, or referenced works**. The common idea is that they help communicate additional meaning about text and its source or context.

- `<abbr>`
- `<cite>`
- `<dfn>`
- `<address>`
- `<blockquote>`
- `<q>`

## `<abbr>` — Abbreviation

`<abbr>` represents an abbreviation or acronym. The `title` attribute can provide the expanded form.

```html
<abbr title="HyperText Markup Language">HTML</abbr>
```

## `<cite>` — Title of a Work

The `<cite>` element is used for the **title of a creative work**.

Examples of works include:

- Books
- Movies
- Songs
- Articles
- Paintings
- Poems
- Research papers

Example:

```html
<p>
  My favorite book is
  <cite>Harry Potter and the Philosopher's Stone</cite>.
</p>
```

## `<dfn>` — Defining a Term

`<dfn>` represents the **defining instance of a term**. This is particularly useful in documentation and educational content.

Example:

```html
<p><dfn>HTML</dfn> is a markup language used to structure web pages.</p>
```

Here:

```text
HTML
 │
 └── term being defined
```

---

## `<address>` — Contact Information

Despite its name, `<address>` is **not simply a tag for writing a postal address**. It represents contact information for the nearest article or the document.

For example:

```html
<address>
  Written by Jane Doe<br />
  Email: example@email.com
</address>
```

It can be used for information about the author or owner of the relevant content.

## `<blockquote>` — Block Quotation

`<blockquote>` represents a **longer quotation** taken from another source. It is a block-level element.

Example:

```html
<blockquote>
  The web should be accessible to everyone, regardless of the device or ability
  they use.
</blockquote>
```

The `cite` attribute identifies the source, but it is not normally displayed as visible text by the browser.

```html
<blockquote cite="https://example.com">The quoted text goes here.</blockquote>
```

## `<q>` — Inline Quotation

`<q>` is used for a **short inline quotation**. Unlike `<blockquote>`, `<q>` fits naturally inside a sentence.

Example:

```html
<p>
  My teacher always says,
  <q>Practice makes progress.</q>
</p>
```

# Highlighting Changes

These elements are particularly useful when a document needs to communicate that information has changed.

- `<del>`
- `<s>`
- `<ins>`

## `<del>` — Deleted Content

The `<del>` element represents content that has been **deleted from a document**.

```html
<del>Old price: $50</del>
```

The browser normally renders it with a strikethrough:

~~Old price: $50~~

## `<s>` — No Longer Accurate or Relevant

The `<s>` element represents content that is **no longer accurate, relevant, or applicable**.

```html
<p>
  <s>Only 10 seats available.</s>
</p>

<p>Now accepting unlimited registrations.</p>
```

This does not necessarily mean that the content was deleted from a previous version of the document. It means that this information is no longer valid.

## `<ins>` — Inserted Content

The `<ins>` element represents content that has been **added to a document**. It is especially useful together with `<del>`.

Example:

```html
<p>
  Price:
  <del>$50</del>
  <ins>$35</ins>
</p>
```

---

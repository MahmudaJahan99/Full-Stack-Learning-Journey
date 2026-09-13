# Grouping Text

As we build an HTML document, we often need to **group related pieces of content together**.

For example, imagine a profile card:

```text
┌─────────────────────────────────┐
│  Jane Doe                       │
│  Frontend Developer             │
│                                 │
│  I am learning full stack       │
│  web development.               │
└─────────────────────────────────┘
```

The browser needs a way to understand that all of this content belongs to one particular group.

HTML provides general-purpose grouping elements for this:

```text
Grouping Text
      │
      ├── <div>  → Block-level container
      │
      └── <span> → Inline container
```

The two elements are:

- `<div>` — groups larger/block-level pieces of content
- `<span>` — groups a small piece of content within a line

---

# `<div>`

`<div>` is a **generic block-level container**. The name comes from **division**. It doesn't tell the browser that its contents are a heading, article, navigation, or paragraph. Instead, it simply says:

> "These elements belong together as a group."

Example:

```html
<div>
  <h2>About Me</h2>
  <p>I am learning full stack web development.</p>
</div>
```

**_`<div>` Is a Block-Level Element_**

By default, `<div>` behaves as a **block-level element**. A block-level element generally starts on a new line and occupies the available width.

For example:

```html
<div>First group</div>
<div>Second group</div>
<div>Third group</div>
```

Conceptually:

```text
┌──────────────────────────────────┐
│ First group                      │
└──────────────────────────────────┘
┌──────────────────────────────────┐
│ Second group                     │
└──────────────────────────────────┘
┌──────────────────────────────────┐
│ Third group                      │
└──────────────────────────────────┘
```

---

# `<span>`

`<span>` is also a generic container, but unlike `<div>`, it is an **inline-level element** by default. It is commonly used to group or identify a small piece of text **within a line**.

Example:

```html
<p>I am learning <span>HTML</span>.</p>
```

The `<span>` doesn't normally create a new line.

```text
I am learning HTML.
              ↑
            <span>
```

---

## Why Do We Need `<span>`?

Suppose we want to give only the word "JavaScript" a special style.

We can wrap that word in a `<span>`:

```html
<p>I love <span>JavaScript</span>.</p>
```

Now CSS can target just that part:

```css
span {
  font-weight: bold;
}
```

---

# `<div>` vs `<span>`

This is one of the most important comparisons in this node.

| `<div>`                           | `<span>`                            |
| --------------------------------- | ----------------------------------- |
| Generic container                 | Generic container                   |
| Block-level                       | Inline                              |
| Starts on a new line              | Stays within the current line       |
| Used for larger groups of content | Used for smaller pieces of content  |
| Can contain many elements         | Commonly used around inline content |
| Page sections/layout containers   | Styling/identifying parts           |

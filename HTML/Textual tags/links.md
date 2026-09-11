# Links — `<a>`

The `<a>` element creates a hyperlink.

```html
<a href="https://example.com">Visit Example</a>
```

The basic structure is:

```text
<a href="destination">
   │       │
   │       └── Where the link goes
   │
   └── Anchor element
```

---

## Basic Link

```html
<a href="https://www.google.com">Google</a>
```

The text between the opening and closing tags is the **link text**.

---

## The `href` Attribute

`href` stands for **hypertext reference**. It specifies the destination of the link.

```html
<a href="https://example.com">Example</a>
```

Here:

```text
href
 ↓
"https://example.com"
```

Without `href`:

```html
<a>Example</a>
```

the element is not a normal functioning hyperlink to a destination.

---

## Absolute URLs

An absolute URL contains the complete web address. Useful when linking to another website.

```html
<a href="https://www.example.com/about"> About </a>
```

---

## Relative URLs

A relative URL points to another resource within your own website.

Suppose your project looks like this:

```text
website/
│
├── index.html
├── about.html
└── contact.html
```

You can write:

```html
<a href="about.html">About</a> <a href="contact.html">Contact</a>
```

The browser interprets these relative to the current page.

---

## Linking to a Section of the Same Page

You can link to an element using its `id`.

```html
<a href="#projects">Go to Projects</a>

<h2 id="projects">My Projects</h2>
```

The `#` tells the browser that `projects` is an ID on the current page.

```text
Click
  │
  ▼
<a href="#projects">
  │
  ▼
Find id="projects"
  │
  ▼
<h2 id="projects">
```

---

## Opening a Link in a New Tab

You can use the `target` attribute:

```html
<a href="https://example.com" target="_blank"> Visit Example </a>
```

`_blank` generally opens the destination in a new browsing context, commonly a new tab.

For external links, it is common to also use:

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
  Visit Example
</a>
```

`rel="noopener noreferrer"` helps prevent the newly opened page from getting access to the opener context and avoids sending referrer information.

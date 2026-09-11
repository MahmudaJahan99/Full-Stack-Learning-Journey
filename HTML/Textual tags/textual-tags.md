# Textual Tags

Textual tags are HTML elements used to display, organize, emphasize, or format text on a webpage. They help the browser understand **what a piece of text represents**, not just how it should look.

For example:

```html
<h1>My Website</h1>
<p>Welcome to my website!</p>
<strong>This is important.</strong>
```

The browser interprets these differently:

```text
                HTML Document
                     │
                     ▼
              ┌─────────────┐
              │    Text     │
              └──────┬──────┘
                     │
       ┌─────────────┼─────────────┐
       ▼             ▼             ▼
    Heading       Paragraph     Emphasis
     <h1>            <p>       <strong>
```


# Quick Reference

| Tag        | Purpose                                            |
| ---------- | -------------------------------------------------- |
| `<h1>`     | Main/most important heading                        |
| `<h2>`     | Level-2 heading                                    |
| `<h3>`     | Level-3 heading                                    |
| `<h4>`     | Level-4 heading                                    |
| `<h5>`     | Level-5 heading                                    |
| `<h6>`     | Level-6 heading                                    |
| `<title>`  | Title of the HTML document                         |
| `<p>`      | Paragraph                                          |
| `<hr>`     | Thematic break                                     |
| `<br>`     | Line break                                         |
| `<b>`      | Draws attention without conveying extra importance |
| `<strong>` | Strong importance                                  |
| `<pre>`    | Preserves whitespace and line breaks               |
| `<i>`      | Text set apart from surrounding content            |
| `<em>`     | Emphasized text                                    |
| `<mark>`   | Highlighted/relevant text                          |
| `<sub>`    | Subscript                                          |
| `<sup>`    | Superscript                                        |
| `<a>`      | Hyperlink                                          |

---

# Semantic HTML: The Bigger Picture

One of the most important ideas behind these tags is that HTML is **semantic**.

Semantic HTML means choosing an element based on **what the content means**, rather than simply how you want it to look.

For example:

```html
<b>Important</b>
```

and

```html
<strong>Important</strong>
```

may look similar in the browser.

But they communicate different meanings.

Likewise:

```html
<i>JavaScript</i>
```

and

```html
<em>really</em>
```

may both appear italic, but their semantic purposes differ.

Think of HTML as giving the browser a description of your content:

```text
HTML
 │
 ├── "This is a heading."
 │        → <h1>
 │
 ├── "This is a paragraph."
 │        → <p>
 │
 ├── "This is important."
 │        → <strong>
 │
 ├── "This is emphasized."
 │        → <em>
 │
 ├── "This is a link."
 │        → <a>
 │
 └── "This text is highlighted."
          → <mark>
```

CSS can then control how those elements **look**.

```text
          HTML
           │
           │ meaning / structure
           ▼
      ┌───────────┐
      │  Content  │
      └─────┬─────┘
            │
            ▼
           CSS
            │
            │ presentation
            ▼
      ┌───────────┐
      │   Style   │
      └───────────┘
```

This separation becomes extremely important as we move deeper into frontend development.

---

# 🧠 Things to Remember

### 1. `<h1>`–`<h6>` represent hierarchy

Don't choose headings based only on their default font size.

### 2. `<title>` is different from `<h1>`

`<title>` belongs in `<head>` and describes the document.

`<h1>` belongs in the page content and represents a major heading.

### 3. `<br>` isn't a spacing tool

Use it for meaningful line breaks, not to create large gaps between elements.

### 4. `<hr>` represents a thematic break

It isn't merely "draw a line."

### 5. `<strong>` and `<em>` carry meaning

They are semantic elements, not simply alternatives to CSS `font-weight` and `font-style`.

### 6. `<pre>` preserves whitespace

This makes it particularly useful for formatted text and code.

### 7. Links use `<a>`

The `href` attribute specifies where the link goes.

### 8. HTML describes meaning; CSS controls presentation

```text
HTML → What is this?
CSS  → How should it look?
JS   → How should it behave?
```

---

# ✍️ Mini Practice

Try creating a small HTML article without using CSS.

Your page should contain:

* One `<h1>` title
* At least two `<h2>` sections
* Paragraphs using `<p>`
* An `<hr>` separating two sections
* A `<strong>` warning
* An `<em>` emphasized phrase
* A `<mark>` highlighted word
* One chemical formula using `<sub>`
* One mathematical expression using `<sup>`
* An ASCII drawing using `<pre>`
* At least two links using `<a>`

### Challenge

Create a page called:

**"My Full Stack Learning Journey"**

Try to make the HTML communicate the structure and meaning of the page **without using CSS**.

Then ask yourself:

> "If someone removed all the styling, would the HTML structure still make sense?"

If the answer is yes, you're starting to think semantically. 🌱

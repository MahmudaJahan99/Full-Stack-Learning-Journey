# Textual Tags

Textual tags are HTML elements used to display, organize, emphasize, or format text on a webpage. They help the browser understand **what a piece of text represents**, not just how it should look.

Example:

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

---

## 🧠 Things to Remember

1. `<h1>`–`<h6>` represent hierarchy
2. `<title>` is different from `<h1>`
3. `<br>` isn't a spacing tool
4. `<hr>` represents a thematic break
5. `<strong>` and `<em>` carry meaning
6. `<pre>` preserves whitespace
7. Links use `<a>` and the `href` attribute specifies where the link goes.

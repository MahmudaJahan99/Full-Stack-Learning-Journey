#External CSS

**External CSS** means putting CSS in a separate `.css` file and connecting that file to the HTML document. This is the most common approach for larger websites.

Example structure:

```text
my-website/
│
├── index.html
│
└── style.css
```

The HTML contains the structure. The CSS file contains the styling.

## Creating an External CSS File

Create a file called:

```text
style.css
```

Inside it:

```css
h1 {
  color: blue;
  font-size: 40px;
}

p {
  color: gray;
}
```

Then connect it to HTML using `<link>`.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Website</title>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <h1>Hello World</h1>
    <p>I am learning CSS.</p>
  </body>
</html>
```

---

## `<link>`

The basic syntax is:

```html
<link rel="stylesheet" href="style.css" />
```

There are two important attributes here.

### `rel`

```html
rel="stylesheet"
```

This tells the browser:

> "The linked resource is a stylesheet."

### `href`

```html
href="style.css"
```

This tells the browser where the stylesheet is located.

---

## External CSS with Folders

CSS files don't have to sit beside the HTML file. The `href` is the path to the stylesheet.

For example:

```text
my-website/
│
├── index.html
│
└── css/
    └── style.css
```

Then:

```html
<link rel="stylesheet" href="css/style.css" />
```

---

### Advantages of External CSS

- Highly reusable
- Better separation of concerns
- Easier maintenance
- Keeps HTML clean
- Consistent design

### Disadvantages of External CSS

- Requires an additional file
- Extra HTTP request
- Dependency on the stylesheet
- Less convenient for tiny, page-specific styles
- Changes can affect multiple pages

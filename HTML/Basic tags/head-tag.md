# 3. `<head>`

The `<head>` element contains **metadata and other information about the HTML document**. The contents of `<head>` generally **aren't displayed** as normal webpage content.

For example:

```html
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My Website</title>
</head>
```

## What goes inside `<head>`?

Common elements include:

```
<head>
│
├── <title>
├── <meta>
├── <link>
├── <style>
└── <script>
```

### `<title>`

The <title> element defines the **title of the document**.

```html
<title>My Portfolio</title>
```

The title may appear in places such as:

- the browser tab
- bookmarks
- browser history
- search engine results

### `<meta>`

The `<meta>` element provides **metadata about the HTML document**. Metadata is information about the webpage that isn't normally displayed as visible content.

For example:

```html
<meta charset="UTF-8" />
```

This tells the browser which character encoding the document uses. UTF-8 supports a very large range of characters and symbols.

Another common example is:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

This helps the webpage display correctly on different screen sizes, especially mobile devices.

Other types of metadata can provide information such as a page description:

```html
<meta name="description" content="My personal portfolio website" />
```

### `<link>`

The `<link>` element is used to **connect the HTML document to an external resource**. One of its most common uses is connecting an external CSS file.

```html
<link rel="stylesheet" href="style.css" />
```

The `<link>` element can also be used for other resources, such as a favicon:

```html
<link rel="icon" href="favicon.icon" />
```

### `<style>`

The `<style>` element is used to write **CSS directly inside the HTML document**.

For example:

```html
<head>
  <style>
    h1 {
      color: blue;
    }

    p {
      font-size: 18px;
    }
  </style>
</head>
```

The `<style>` element itself isn't displayed on the webpage. It contains CSS rules that control how elements in the page look.

### <script>

The <script> element is used to **include or write JavaScript**. JavaScript allows webpages to have dynamic behavior and respond to user interactions.

For example:

```html
<script>
  alert("Hello!");
</script>

<script src="script.js"></script>
```

## `<head>` vs `<body>`

This distinction is extremely important.

`<head>` - Contains information about the document and resources/settings needed by the page.

`<body>` - Contains the actual document content displayed to the user.

```
                    HTML
                      │
             ┌────────┴────────┐
             │                 │
             ▼                 ▼
           HEAD              BODY
             │                 │
             │                 │
       Page setup/info     Page content
             │                 │
       ┌─────┼─────┬─────┐     ├── Headings
       │     │     │     │     ├── Paragraphs
       ▼     ▼     ▼     ▼     ├── Images
    title  meta  link style     ├── Links
                    │     │     ├── Forms
                    │     └── CSS
                    └── External resources

                         script
                           │
                           └── JavaScript
```

```
<head>
    → Information and resources for the document
    → Usually not visible as page content

<body>
    → Actual webpage content
    → Displayed to the user
</body>
```

# `<title>`

The `<title>` element defines the title of the HTML document. It is placed inside `<head>`.

```html
<head>
  <title>My Portfolio</title>
</head>
```

The title usually appears in:

- Browser tabs
- Bookmarks
- Search engine results

## Example

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Mahmuda's Portfolio</title>
  </head>

  <body>
    <h1>Welcome to My Portfolio</h1>
  </body>
</html>
```

Conceptually:

```text
<title>
    ↓
Browser/document title
        │
        ▼
┌───────────────────────────┐
│ Mahmuda's Portfolio    ×  │ ← Browser tab
└───────────────────────────┘


<h1>
    ↓
Content visible inside page
        │
        ▼
┌───────────────────────────┐
│ Welcome to My Portfolio   │
│                           │
│      Page content...      │
└───────────────────────────┘
```

### `<title>` vs `<h1>`

| `<title>`                   | `<h1>`                 |
| --------------------------- | ---------------------- |
| Goes inside `<head>`        | Goes inside `<body>`   |
| Document/page title         | Visible main heading   |
| Appears in browser tab      | Appears on the webpage |
| Not visible in page content | Visible to users       |

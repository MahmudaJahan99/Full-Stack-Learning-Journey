# `<html>`

The `<html>` element is the **root element** of an HTML document. Everything except the DOCTYPE declaration belongs inside it.

```
<!DOCTYPE html>

       │
       │ declaration
       ▼

    <html>
       │
       ├── <head>
       │
       └── <body>
```

The `<html>` element contains the two major parts of an HTML document - head and body

## The lang attribute

The lang attribute specifies the primary language of the document.

For English:

```html
<html lang="en">
  ...
</html>
```

For Bengali:

```html
<html lang="bn">
  ...
</html>
```

For Japanese:

```html
<html lang="ja">
  ...
</html>
```

### This information can be useful to:

- screen readers
- browsers
- search engines
- translation tools
- accessibility technologies

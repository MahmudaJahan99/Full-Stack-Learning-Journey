# Internal CSS

**Internal CSS** is CSS written inside a `<style>` element in the HTML document. The `<style>` element is normally placed inside `<head>`.

Syntax

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      selector {
        property: value;
      }
    </style>
  </head>

  <body>
    ...
  </body>
</html>
```

Example:

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 {
        color: blue;
        font-size: 40px;
      }

      p {
        color: gray;
      }
    </style>
  </head>

  <body>
    <h1>Hello World</h1>
    <p>I am learning CSS.</p>
  </body>
</html>
```

Internal CSS goes inside `<style>...</style>` which is normally placed in `<head></head>`

### Advantages of Internal CSS

- Less repetition
- Keeps styles together
- Useful for single-page websites
- Easier to maintain than inline CSS
- No separate stylesheet required

### Disadvantages of Internal CSS

- Limited reusability across pages
- CSS must be repeated
- HTML file becomes larger
- Poor separation of concerns
- Harder to maintain large website

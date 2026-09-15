# Including JavaScript

JavaScript can be added to an HTML document in several ways. The most common approach is to use the `<script>` element.

## What is JavaScript?

**JavaScript** is a programming language used to add **behavior and interactivity** to web pages. JavaScript can be used to:

- Respond to button clicks
- Validate forms
- Change HTML content
- Modify CSS styles
- Create interactive components
- Fetch data from APIs

### The `<script>` Tag

The JavaScript code is placed between the opening and closing `<script>` tags. The `<script>` element is used to include JavaScript in an HTML document.

```html
<script>
  console.log("Hello, World!");
</script>
```

---

### Inline JavaScript

JavaScript can be written directly inside an HTML element using an event attribute.

```html
<button onclick="alert('Hello!')">Click Me</button>
```

Here, `onclick` runs the JavaScript when the button is clicked.

### Internal JavaScript

JavaScript can be written inside a `<script>` element within the HTML document.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Internal JavaScript</title>
  </head>

  <body>
    <button id="btn">Click Me</button>

    <script>
      const button = document.getElementById("btn");

      button.addEventListener("click", () => {
        alert("Hello!");
      });
    </script>
  </body>
</html>
```

The JavaScript belongs to that particular HTML document.

### External JavaScript

The `src` attribute specifies the location of the JavaScript file. JavaScript can be placed in a separate `.js` file and connected to HTML.

`script.js`

```javascript
console.log("Hello from JavaScript!");
```

`index.html`

```html
<script src="script.js"></script>
```

#### Where Should the `<script>` Go?

A script can be placed in the `<head>` or `<body>`. However, when loading external JavaScript, two important attributes are commonly used - **defer** and **async**.

```html
<script src="script.js" defer></script>
```

`defer` tells the browser to download the JavaScript while parsing the HTML but execute it after the HTML has been parsed. This is generally useful for scripts that interact with the page's HTML.

```html
<script src="script.js" async></script>
```

With `async`, the script downloads independently and executes as soon as it is ready.This means its execution may happen before the HTML has finished parsing.

| `defer`                                 | `async`                                     |
| --------------------------------------- | ------------------------------------------- |
| Downloads while HTML is parsed          | Downloads while HTML is parsed              |
| Executes after HTML parsing             | Executes as soon as it finishes downloading |
| Deferred scripts maintain order         | Async scripts do not guarantee order        |
| Useful for scripts depending on the DOM | Useful for independent scripts              |

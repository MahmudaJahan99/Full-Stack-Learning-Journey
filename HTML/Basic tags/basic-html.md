# The Basic HTML Document

A standard HTML document can look like this:

```html
<!DOCTYPE html>

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My First Webpage</title>
  </head>

  <body>
    <h1>Hello, World!</h1>
    <p>This is my first webpage.</p>
  </body>
</html>
```

Structure visualization:

```
                    HTML DOCUMENT
                         │
                         ▼
                  <!DOCTYPE html>
                         │
                         ▼
                     <html>
                    /      \
                   /        \
                  ▼          ▼
              <head>       <body>
                │             │
                │             ├── Visible content
                │             ├── <h1>
                │             ├── <p>
                │             └── ...
                │
                ├── <meta>
                ├── <title>
                └── ...
```

Think of it as the **skeleton** of the webpage.
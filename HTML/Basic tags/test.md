

🧠 How the Browser Thinks About It

Suppose the browser receives:

<!DOCTYPE html>

<html>
    <head>
        <title>My Page</title>
    </head>

    <body>
        <h1>Hello!</h1>
    </body>

</html>

The browser can conceptually interpret the document like:

Document
│
└── html
│
├── head
│ └── title
│ └── "My Page"
│
└── body
└── h1
└── "Hello!"

This tree-like representation is the foundation for the DOM.

You don't need to learn the DOM yet — just remember that HTML has a hierarchical structure.

⚠️ Common Beginner Mistakes

1. Putting visible content inside <head>

Avoid:

<head>
    <h1>Hello World</h1>
</head>

Visible page content belongs in:

<body>
    <h1>Hello World</h1>
</body>
2. Putting <head> and <body> outside <html>

Avoid:

<head>
    ...
</head>

<html>
    ...
</html>

They belong inside <html>:

<html>

    <head>
        ...
    </head>

    <body>
        ...
    </body>

</html>
3. Forgetting the DOCTYPE

Technically, browsers can still process HTML without it, but a proper modern HTML document should begin with:

<!DOCTYPE html>

It ensures standards mode is used.

4. Writing the viewport meta tag incorrectly

Use the standard form:

<meta name="viewport"
      content="width=device-width, initial-scale=1.0">

Don't confuse it with:

<meta charset="UTF-8">

They serve different purposes.

charset
↓
How characters are interpreted

viewport
↓
How the page's viewport behaves 5. Thinking <meta> creates visible content

This:

<meta charset="UTF-8">

doesn't display:

UTF-8

on the webpage.

It provides information to the browser about the document.

📊 Quick Comparison
Element Purpose Visible on page? Closing tag?

<!DOCTYPE html>	Declares HTML document type	❌	❌
<html>	Root of the document	❌	✅
<head>	Contains document metadata/resources	❌	✅
<body>	Contains webpage content	✅	✅
<meta>	Provides metadata	❌	❌

Note: <html>, <head>, and <body> are structural elements. They organize the document rather than being content that users directly see.

🧪 Practice

Create an index.html file containing:

<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>My HTML Journey</title>

</head>

<body>

    <h1>My HTML Journey</h1>

    <p>
        I am learning how HTML documents are structured.
    </p>

</body>

</html>

Then experiment.

Change the language

<html lang="bn">
Change the title
<title>Mahmuda's Web Development Journey</title>
Add another element to the body
<p>I am learning the fundamentals of web development.</p>

Notice that the title appears in the browser tab, while the paragraph appears in the webpage itself.

🎯 Key Takeaways

<!DOCTYPE html>

Declares that the document uses modern HTML and puts the browser into standards mode.

<html>

The root element containing the entire HTML document.

<html lang="en">
    ...
</html>
<head>

Contains metadata and resources/information about the document.

<head>
    <meta ...>
    <title>...</title>
</head>
<body>

Contains the actual content of the webpage.

<body>
    <h1>Hello</h1>
    <p>Welcome!</p>
</body>
<meta>

Provides metadata about the document.

Two particularly important examples:

<meta charset="UTF-8">

and:

<meta name="viewport"
      content="width=device-width, initial-scale=1.0">
🧠 The Mental Model

If you remember only one diagram from this chapter, remember this:

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
                │             │
        Document information  │
                │             │
          ┌─────┴─────┐       │
          │           │       │
       <meta>      <title>    │
                              │
                              ▼
                         Page content
                              │
                    ┌─────────┼─────────┐
                    │         │         │
                   <h1>       <p>       ...

The fundamental relationship is:

<html> contains <head> and <body>.

<head> describes the document.

<body> contains the document's content.

<meta> provides metadata.

<!DOCTYPE html> tells the browser what kind of document it is dealing with.

🔗 What comes next?

Now that we understand the skeleton of an HTML document, we're ready to start putting actual content inside the <body>.

The next roadmap section moves into Textual Tags, where we'll learn how to represent headings, paragraphs, emphasis, quotations, and other types of textual content.

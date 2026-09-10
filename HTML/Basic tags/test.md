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

---

## 1. <!DOCTYPE>

This is called the **DOCTYPE declaration**. It tells the browser which HTML standard the document is intended to follow.

```html
<!DOCTYPE html>
```

Technically <!DOCTYPE> is not an HTML tag. It is a **declaration**, not an HTML element. That's why it doesn't look like the other HTML elements. It also doesn't have a closing tag.

### Why do we need it?

The DOCTYPE declaration helps the browser **render the document using standards mode** rather than an older compatibility mode. Historically, HTML doctypes were much more complicated.

### Where does it go?

It should be the first thing in the HTML document:

<!DOCTYPE html> tells the browser to interpret the document as modern HTML and use standards mode. It doesn't create an element and it doesn't appear on the webpage.

---

## 2. <html>

The <html> element is the root element of an HTML document.

Everything except the DOCTYPE declaration belongs inside it.

<!DOCTYPE html>

<html>
    ...
</html>

Visualized:

<!DOCTYPE html>

       │
       │ declaration
       ▼

    <html>
       │
       ├── <head>
       │
       └── <body>

The <html> element contains the two major parts of an HTML document:

<html>
│
├── <head>
│
└── <body>
The lang attribute

You'll commonly see:

<html lang="en">

The lang attribute specifies the primary language of the document.

For English:

<html lang="en">

For Bengali:

<html lang="bn">

For Japanese:

<html lang="ja">

For a Bengali webpage:

<html lang="bn">

This information can be useful to:

screen readers
browsers
search engines
translation tools
accessibility technologies

So a good starting point is:

<html lang="en">

or whatever language your document primarily uses.

<html> is the root

Consider this document:

<html>
    <head>
        ...
    </head>

    <body>
        ...
    </body>

</html>

We can represent it as a tree:

html
│
├── head
│
└── body

This hierarchical structure is fundamental to HTML.

Later, this same structure will be represented in the DOM (Document Object Model).

3. <head>

The <head> element contains metadata and other information about the HTML document.

<head>
    ...
</head>

The contents of <head> generally aren't displayed as normal webpage content.

For example:

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>My Website</title>

</head>
What goes inside <head>?

Common elements include:

<head>
│
├── <title>
├── <meta>
├── <link>
├── <style>
└── <script>

We'll encounter many of these later in the roadmap.

For now, focus on <title> and <meta>.

<title>

The <title> element defines the title of the document.

<title>My Portfolio</title>

The title may appear in places such as:

the browser tab
bookmarks
browser history
search engine results

For example:

┌─────────────────────────────────────────────┐
│ 🌐 My Portfolio | Chrome │
├─────────────────────────────────────────────┤
│ │
│ My Portfolio │
│ │
└─────────────────────────────────────────────┘

The <title> itself isn't normally displayed inside the webpage.

<head> vs <body>

This distinction is extremely important.

<head>

Contains information about the document and resources/settings needed by the page.

<head>
    <meta charset="UTF-8">
    <title>My Website</title>
</head>
<body>

Contains the actual document content displayed to the user.

<body>
    <h1>Welcome!</h1>
    <p>Hello, world!</p>
</body>

Think:

              HTML
                │
       ┌────────┴────────┐
       │                 │
       ▼                 ▼
     HEAD               BODY
       │                 │
       │                 │
       ▼                 ▼

Document information Page content
│ │
▼ ▼
Metadata Headings
Title Paragraphs
Links Images
etc. Forms
etc. 4. <body>

The <body> element contains the content of the HTML document.

<body>

    <h1>Welcome to my website</h1>

    <p>This is my webpage.</p>

</body>

This is where most of the content users interact with is placed.

Examples include:

headings
paragraphs
images
links
buttons
lists
forms
videos
navigation
articles
sections

We'll learn these elements later.

Example

<body>

    <h1>My Portfolio</h1>

    <p>Hello! I'm learning frontend development.</p>

    <a href="projects.html">View my projects</a>

</body>

The browser renders the content inside the body as part of the webpage.

Conceptually:

HTML document
│
├── HEAD
│ ├── Metadata
│ ├── Title
│ └── Other document information
│
└── BODY
├── Heading
├── Paragraph
├── Link
└── Other visible content 5. <meta>

The <meta> element provides metadata about the HTML document.

"Metadata" simply means:

Data about data.

In this case, it means information about the webpage/document.

A <meta> element looks like:

<meta ...>

It doesn't contain visible page content and doesn't require a closing tag.

Character Encoding

One of the most important <meta> declarations is:

<meta charset="UTF-8">

This specifies the document's character encoding.

What is character encoding?

Computers store information as numbers/bits, but text contains characters such as:

A B C
1 2 3
বাংলা
中文
日本語
é
©
😊

Character encoding defines how those characters are represented digitally.

UTF-8 is a widely used encoding capable of representing characters from many writing systems.

Therefore, we commonly put this near the beginning of <head>:

<head>
    <meta charset="UTF-8">
</head>

This helps the browser correctly interpret the characters in your document.

Why UTF-8 matters

Without appropriate character encoding, text can sometimes be displayed incorrectly.

For example, instead of:

বাংলা ভাষা

you might encounter incorrectly interpreted characters.

Using:

<meta charset="UTF-8">

helps the browser interpret the document using UTF-8.

6. The Viewport Meta Tag

Another extremely common <meta> element is:

<meta name="viewport"
      content="width=device-width, initial-scale=1.0">

You'll see this in almost every modern HTML starter template.

Why is it needed?

Websites are viewed on many different devices:

Desktop Tablet Phone

┌───────────────┐ ┌───────────┐ ┌───────┐
│ │ │ │ │ │
│ │ │ │ │ │
│ │ │ │ │ │
│ │ │ │ │ │
└───────────────┘ └───────────┘ └───────┘

The viewport is essentially the area of the webpage that is visible to the user.

This meta declaration tells the browser how to treat the page's viewport on different devices.

<meta name="viewport"
      content="width=device-width, initial-scale=1.0">
width=device-width

This tells the browser:

Make the viewport width correspond to the device's screen width.

initial-scale=1.0

This sets the initial zoom level to 1.

Together:

<meta name="viewport"
      content="width=device-width, initial-scale=1.0">

helps establish an appropriate starting viewport for responsive webpages.

We'll study responsive design later when we reach CSS.

7. Other <meta> Information

The <meta> element can provide different kinds of metadata.

For example:

<meta name="description"
      content="A personal portfolio website.">

This provides a description of the page.

Another example:

<meta name="author"
      content="Mahmuda">

This provides author information.

So <meta> isn't one specific piece of information.

It is a general element used to provide metadata in different forms.

🧩 Putting the Basic Tags Together

Now let's assemble everything:

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <title>My First Webpage</title>

</head>

<body>

    <h1>Hello, World!</h1>

    <p>Welcome to my first webpage.</p>

</body>

</html>

Let's break it down:

<!DOCTYPE html>

│
└── Document type declaration
│
▼

<html>
│
├── <head>
│ │
│ ├── <meta charset="UTF-8">
│ │
│ ├── <meta name="viewport" ...>
│ │
│ └── <title>
│
└── <body>
│
├── <h1>
│
└── <p>
🔬 A Closer Look at the Structure

We can think of the document as nested containers:

┌─────────────────────────────────────────────┐
│ <!DOCTYPE html> │
│ │
│ ┌─────────────────────────────────────────┐ │
│ │ <html> │ │
│ │ │ │
│ │ ┌─────────────────────────────────────┐ │ │
│ │ │ <head> │ │ │
│ │ │ │ │ │
│ │ │ <meta> │ │ │
│ │ │ <meta> │ │ │
│ │ │ <title>...</title> │ │ │
│ │ │ │ │ │
│ │ └─────────────────────────────────────┘ │ │
│ │ │ │
│ │ ┌─────────────────────────────────────┐ │ │
│ │ │ <body> │ │ │
│ │ │ │ │ │
│ │ │ <h1>...</h1> │ │ │
│ │ │ <p>...</p> │ │ │
│ │ │ │ │ │
│ │ └─────────────────────────────────────┘ │ │
│ │ │ │
│ └─────────────────────────────────────────┘ │
└─────────────────────────────────────────────┘

This is the basic skeleton you'll encounter in almost every HTML document.

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

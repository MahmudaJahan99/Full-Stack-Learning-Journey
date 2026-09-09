# Creating First HTML File

> An HTML document is simply a text file containing HTML markup. The file normally uses the **.html** extension.

For example:

index.html

```html
<!DOCTYPE html>

<html>
  <head>
    <title>My First HTML Page</title>
  </head>

  <body>
    <h1>Hello, World!</h1>
    <p>This is my first HTML page.</p>
  </body>
</html>
```

## Understanding HTML Tags

HTML uses tags to mark up content.

Consider:

```html
<h1>Hello World</h1>
```

Together, the opening tag, content, and closing tag form an HTML element:

```
┌─────────────────────────────────┐
│ <h1> Hello World </h1>          │
│  └─┬─┘ └────┬────┘ └───┬───┘   │
│    │         │          │       │
│ opening    content    closing   │
│   tag                  tag      │
└─────────────────────────────────┘
```

---

## Tag vs Element

**Tag** - A tag is the markup itself.

```
<h1>
```

or:

```
</h1>
```

**Element** - An element consists of the complete structure.

```html
<h1>Hello World</h1>
```

> Tags are used to create elements.

### Different Types of Elements

Most familiar HTML elements have an **opening and closing tag**:

```html
<p>Hello</p>
<h1>Heading</h1>
<a href="https://example.com">Visit Example</a>
```

However, some HTML elements don't wrap content.

For example:

```html
<img src="cat.jpg" alt="A cat" />
```

These are commonly called **void elements**.

Examples include:

```html
<img />
<br />
<hr />
<input />
<meta />
<link />
```

### Tags and Attributes

HTML elements can contain attributes. Attributes provide **additional information** about an element or **modify its behaviour**.

Example:

```html
<a href="https://example.com">
  │ └──────────────┬──────────────┘ │ │ │ Attribute │ └── Element
</a>
```

More specifically:

```
href = "https://example.com"
│       └─────────────────┘
│              │
│           value
│
└── attribute name
```

The general form is:

```html
<tag attribute="value"></tag>
```

An element can have multiple attributes:

```html
<a href="https://example.com" target="\_blank" title="Visit Example">
  Visit Example
</a>
```

### Attribute values

Attribute values are generally written inside quotation marks. **Double quotes** are the conventional choice. **Single quotes** are also used. Both are valid in HTML, but be consistent with one style.

```html
<img src="cat.jpg" />

or

<img src="cat.jpg" />
```

---

## Case Insensitivity

HTML is generally **case-insensitive** when interpreting element and attribute names.

For example, browsers will generally interpret these as the same element:

```html
<p>Hello</p>
<P>Hello</P>
<P>HELLO</p>
```

🚨 However... One should still write HTML in **lowercase**

Lowercase HTML:

- is easier to read
- is easier to maintain
- follows modern conventions
- reduces visual noise

---

## HTML Entities

Sometimes we need to display characters that have a special meaning in HTML. HTML provides character references, commonly called **HTML entities**, to represent such characters safely.

For example:

```html
&lt; represents <
```

### Common HTML Entities

Here are some useful character references:

| Character | Entity   | Meaning               |
| --------- | -------- | --------------------- |
| <         | &lt;     | Less-than             |
| >         | &gt;     | Greater-than          |
| &         | &amp;    | Ampersand             |
| "         | &quot;   | Double quotation mark |
| '         | &apos;   | Apostrophe            |
| ©         | &copy;   | Copyright             |
| ®         | &reg;    | Registered trademark  |
| `&nbsp;`  | `&nbsp;` | Non-breaking space    |

### Entity structure

HTML character references commonly follow this pattern:

`& + name + ;`

For example:

```
&amp;
│  ││
│  │└── semicolon
│  └── entity name
└── starts with &
```

Some can also use a numeric form:

```html
&#60;
```

---

## HTML Comments

Comments allow developers to leave **notes inside HTML code that aren't displayed as part of the webpage**.

HTML comments use:

```html
<!-- This is a comment -->
```

The browser doesn't display the comment as webpage content.

### Why use comments?

Comments can help **explain code**.

```html
<!-- Navigation menu -->
<nav>...</nav>
```

They can **separate sections**.

```html
<!-- ===== Hero Section ===== -->
<section>...</section>
```

They can **temporarily disable** a piece of markup during development.

```html
<!--
<div>
    This is temporarily disabled.
</div>
-->
```

**Important: comments are not secret**

HTML comments are sent to the browser as part of the HTML source Therefore, don't put sensitive information inside comments.

---

## Whitespace

Whitespace refers to **spaces, tabs, and line breaks** in your HTML source.

For example:

```html
<p>Hello World</p>
```

and:

```html
<p>Hello World</p>
```

Both represent essentially the same paragraph. HTML generally collapses consecutive whitespace when rendering normal text.

For example:

```
<p>Hello       World</p>
```

will generally be displayed as:

```
Hello World
```

rather than:

```
Hello       World
```

### Spaces, tabs and new lines

Consider:

```
<p>
    Hello
    World
</p>
```

The browser generally renders this as:

```
Hello World
```

The new line and indentation in the source don't automatically become visible formatting.

**Why do we use whitespace then?**

Because developers need to read the code.

Compare:

```
<html><head><title>My Page</title></head><body><h1>Hello</h1><p>Welcome!</p></body></html>
```

with:

```html
<html>
  <head>
    <title>My Page</title>
  </head>

  <body>
    <h1>Hello</h1>
    <p>Welcome!</p>
  </body>
</html>
```

Whitespace therefore **improves code readability and maintainability**, even when it doesn't change the rendered result.

### Whitespace inside text

There are situations where whitespace does matter. For example, the **<pre>** element preserves whitespace and line breaks:

```html
<pre>
Hello
        World
            !
</pre>
```

The browser preserves the formatting inside <pre>.

---

# 🧠 Putting Everything Together

Let's examine a small HTML document:

```html
<!DOCTYPE html>

<html>
  <head>
    <title>My First Page</title>
  </head>

  <body>
    <!-- Main heading -->
    <h1 class="title">Hello, World!</h1>

    <p>HTML is <strong>fun</strong> &amp; powerful.</p>

    <p>5 &lt; 10</p>
  </body>
</html>
```

```html
<!DOCTYPE html>

│ └── Document declaration

<html>
  │ └── HTML element

  <h1 class="title">
    │ │ │ └── Attribute │ └── Tag

    <!-- Main heading -->

    │ └── Comment

    <strong>fun</strong>
    │ │ │ └── Content │ └── Element &amp; │ └── HTML entity Whitespace /
    indentation │ └── Makes source code easier to read
  </h1>
</html>
```

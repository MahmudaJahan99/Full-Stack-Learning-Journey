# Browsers and How They Work

> A **web browser** is software that allows users to access and interact with resources available on the web.

Examples include:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

A browser does much more than simply "display websites." It:

- Sends HTTP requests
- Resolves domain names through DNS
- Receives server responses
- Parses HTML
- Parses CSS
- Executes JavaScript
- Loads images and other resources
- Builds the page
- Renders pixels on the screen
- Handles user interactions

## Browser Architecture

Different browsers use different implementations, but the basic responsibilities are similar. A simplified view of a browser looks like:

```text
Browser
│
├── User Interface
│
├── Browser Engine
│
├── Rendering Engine
│
├── JavaScript Engine
│
├── Networking
│
└── Storage
```

## What Happens When We Visit a Website?

Suppose we visit:

```text
https://example.com
```

A simplified sequence is:

```text
1. Enter URL
       ↓
2. Browser processes URL
       ↓
3. DNS lookup
       ↓
4. Find server IP
       ↓
5. Establish connection
       ↓
6. Send HTTP request
       ↓
7. Server processes request
       ↓
8. Server sends response
       ↓
9. Browser receives HTML
       ↓
10. Browser requests additional resources
       ↓
11. HTML + CSS + JavaScript are processed
       ↓
12. Browser renders the page
```

---

## HTML Parsing

The browser receives HTML and parses it into a structure called the **DOM (Document Object Model)**. The browser creates a tree-like structure called the **DOM tree**. JavaScript can interact with this structure to change the page.

Example:

```html
<h1>Hello</h1>
<p>Welcome to my website.</p>
```

```text
Document
   |
   ├── h1
   |    └── "Hello"
   |
   └── p
        └── "Welcome to my website."
```

## CSS Parsing

The browser also processes CSS. The browser determines how elements should look and creates structures used during rendering.

Conceptually:

```text
HTML
 ↓
DOM

CSS
 ↓
CSS Rules

DOM + CSS
 ↓
Visual Representation
```

## JavaScript Execution

JavaScript can modify the page and respond to user interactions. The browser's JavaScript engine executes the code. Different browsers use different JavaScript engines.

Example:

```text
Chrome / Edge → V8
Firefox       → SpiderMonkey
Safari        → JavaScriptCore
```

---

## Rendering the Page

The browser combines the information obtained from HTML and CSS to determine what should appear on the screen. The actual browser rendering pipeline is more complex.

A simplified model is:

```text
HTML
 ↓
DOM
 ↓
        ┌──────────────┐
CSS →   │ Rendering    │
        │ Process      │
        └──────────────┘
               ↓
          Layout / Paint
               ↓
             Screen
```

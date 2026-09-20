# Introduction to JavaScript

JavaScript is one of the core technologies of the Web, alongside **HTML** and **CSS**.

- **HTML** → structures the content
- **CSS** → styles the content
- **JavaScript** → adds behavior and interactivity

> JavaScript (JS) is a high-level, dynamically typed, interpreted/JIT-compiled programming language commonly used to add behavior, logic, and interactivity to applications. It was originally created for web browsers, but today JavaScript can run in many different environments.

JavaScript can be used to:

- Change HTML content
- Change CSS styles
- Respond to user interactions
- Validate forms
- Create animations and interactive UI
- Make HTTP requests and communicate with APIs
- Store data in the browser
- Build complete web applications
- Create backend applications
- Build command-line tools
- Create desktop and mobile applications
- Build real-time applications
- Work with databases through server-side environments

---

# History of JavaScript

JavaScript has a relatively unusual history because it was created very quickly during the early development of the Web.

### The Beginning

In **1995**, Netscape Communications wanted a scripting language for its web browser, Netscape Navigator. Netscape hired **Brendan Eich** to create the language. He created the first version of the language in _approximately 10 days_.
The language was initially developed under the name **"Mocha"**. It was later renamed **"LiveScript"** and eventually **"JavaScript"**.

🚨 Despite the similar name, JavaScript and Java are different programming languages.

```text
Java ≠ JavaScript
```

The name "JavaScript" was partly influenced by the popularity of Java at the time and the relationship between Netscape and Sun Microsystems.

### JavaScript in Netscape Navigator

JavaScript was introduced into **Netscape Navigator 2.0 in 1995**. Its original purpose was mainly to allow web pages to become more **dynamic and interactive**. Before JavaScript, web pages were largely static, with JavaScript, pages could respond to user actions directly in the browser. This helped establish the foundation for modern interactive web applications.

### JavaScript and ECMAScript

As JavaScript became popular, different browsers began implementing their own versions of the language. This created a problem and a common standard was needed.

JavaScript was submitted to **Ecma International** for standardization. The standardized language specification became known as **"ECMAScript"**.

```text
JavaScript
    │
    ▼
Language implementation / ecosystem

ECMAScript
    │
    ▼
Standard / specification
```

### JavaScript vs ECMAScript

These terms are related but are not exactly interchangeable. ECMAScript is the _standardized language specification_. JavaScript is a _programming language implementation/ecosystem based on the ECMAScript standard_, together with additional APIs and environments.

---

# JavaScript Versions

JavaScript has evolved significantly over time. The important versions and milestones include:

| Version         | Year | Important Information                         |
| --------------- | ---- | --------------------------------------------- |
| ECMAScript 1    | 1997 | First standardized version                    |
| ECMAScript 2    | 1998 | Editorial changes                             |
| ECMAScript 3    | 1999 | Major early version                           |
| ECMAScript 4    | —    | Abandoned                                     |
| ECMAScript 5    | 2009 | Major improvements                            |
| ECMAScript 5.1  | 2011 | Standardized update                           |
| ECMAScript 2015 | 2015 | Major modernization                           |
| ECMAScript 2016 | 2016 | Smaller yearly release                        |
| ECMAScript 2017 | 2017 | Async/await and other features                |
| ECMAScript 2018 | 2018 | Rest/spread improvements and more             |
| ECMAScript 2019 | 2019 | Array and object improvements                 |
| ECMAScript 2020 | 2020 | BigInt, optional chaining, nullish coalescing |
| ECMAScript 2021 | 2021 | Logical assignment and other features         |
| ECMAScript 2022 | 2022 | Class fields and other features               |
| ECMAScript 2023 | 2023 | Array and hashbang improvements               |
| ECMAScript 2024 | 2024 | New language and API features                 |
| ECMAScript 2025 | 2025 | Continued annual evolution                    |

ECMAScript has followed an annual release cycle since ES2015 and continues to receive yearly updates.

## ES5

One of the important milestones in JavaScript history was ECMAScript 5 (ES5), released in 2009. ES5 introduced or standardized many features that became widely used in JavaScript.

For example:

"use strict";

and methods such as:

Array.prototype.forEach()
Array.prototype.map()
Array.prototype.filter()
Array.prototype.reduce()

## ES6

ECMAScript 2015, commonly called ES6, was one of the most significant updates in JavaScript history. It introduced many important features, including:

- let
- const
- Arrow functions
- Template literals
- Destructuring
- Default parameters
- Rest parameters
- Spread syntax
- Classes
- Modules
- Promises
- Map
- Set
- Enhanced object syntax

Example:

Traditional function:

```js
function add(a, b) {
  return a + b;
}
```

Arrow function:

```js
const add = (a, b) => {
  return a + b;
};

// Or

const add = (a, b) => a + b;
```

## ES2017

Introduced **async** and **await**.

Example:

```js
async function getData() {
  const response = await fetch("/api/data");
  const data = await response.json();

  console.log(data);
}
```

## ES2020

Introduced features such as **optional chaining**, **Nullish coalescing**, and **BigInt**.

Example:

```js
const user = {};

console.log(user?.profile?.name);
```

Instead of causing an error when profile does not exist, optional chaining safely returns _undefined_.

---

# How to Run JavaScript

There are several ways to run JavaScript.

```text
                    JavaScript
                         │
          ┌──────────────┼──────────────┐
          │              │              │
       Browser         Node.js       Other
          │              │
          │              ├── Terminal
          │              ├── Scripts
          │              └── Server
          │
          ├── Console
          ├── <script>
          └── DevTools
```

## Run JavaScript in the Browser Console

The easiest way to experiment with JavaScript is through a browser's Developer Tools Console.

For example, in Chrome:

```text
Right Click
↓
Inspect
↓
Console
```

Then write `console.log("Hello, JavaScript!");`

Press Enter.

We should see:

```text
Hello, JavaScript!
```

The browser console is extremely useful for:

- Testing small pieces of code
- Debugging
- Inspecting values
- Learning JavaScript
- Experimenting with browser APIs

## JavaScript Inside an HTML File

JavaScript can be written directly inside an HTML document using the <script> element.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>JavaScript</title>
  </head>
  <body>
    <h1>Hello World</h1>

    <script>
      console.log("Hello from JavaScript!");
    </script>
  </body>
</html>
```

This is called inline JavaScript when the JavaScript code is written directly inside the HTML file. The JavaScript is placed between `<script>// JavaScript goes here</script>`

## External JavaScript File

For larger projects, JavaScript is normally placed in a separate .js file.

The file structure could look like:

project/
│
├── index.html
└── script.js

The HTML connects to JavaScript using:

```html
<script src="script.js"></script>
```

An external file helps with:

- Organization
- Maintainability
- Reusability
- Separation of concerns
- Cleaner HTML

## Running JavaScript with Node.js

JavaScript is not limited to browsers. Node.js allows JavaScript to run outside the browser.

For example, create `hello.js` with:

```js
console.log("Hello from Node.js!");
```

Then run `node hello.js`

Output:

```
Hello from Node.js!
```

Node.js makes it possible to use JavaScript for things such as:

- Backend development
- APIs
- Command-line tools
- Automation
- Server applications
- Build tools

### Using the Node.js REPL

Node.js also provides an interactive environment called the REPL.

REPL stands for **Read Evaluate Print Loop**

Run `node`

We can then write:

```
> 10 + 20
> 30
```

To exit:

```
.exit
```

or press `Ctrl + C`

## Running JavaScript with Code Editors

Modern code editors such as Visual Studio Code provide an environment for writing JavaScript. A typical setup might look like:

JavaScript Project
│
├── index.html
├── style.css
└── script.js

We can write JavaScript in **`script.js`** and execute it either through:

- A browser
- Browser DevTools
- Node.js
- A development server
- A framework/toolchain

---

# JavaScript Runtime

A JavaScript runtime environment provides everything necessary for JavaScript code to execute. Examples include Browser, Node.js, Deno, and Bun.

A runtime generally provides:

```text
JavaScript Code
│
▼
JavaScript Engine
│
▼
Host Environment APIs
│
▼
Program Execution
```

Browsers contain JavaScript engines. Different browsers use different engines:

- Environment JavaScript Engine
- Google Chrome V8
- Microsoft Edge V8
- Firefox SpiderMonkey
- Safari JavaScriptCore
- Node.js also uses V8.

---

## JavaScript Engine

A JavaScript engine is the component responsible for executing JavaScript code.

```text
JavaScript Code
│
▼
JavaScript Engine
│
▼
Machine-level instructions
│
▼
Execution
```

Some well-known JavaScript engines are:

- V8 → Chrome, Edge, Node.js
- SpiderMonkey → Firefox
- JavaScriptCore → Safari

Modern JavaScript engines use techniques such as Just-In-Time (JIT) compilation to improve performance.

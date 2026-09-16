# CSS

> **CSS** stands for **Cascading Style Sheets**. It is the language used to control the **visual presentation and layout of web pages**. HTML provides the **structure** of a webpage, CSS controls its **appearance**, and JavaScript adds **behavior and interactivity**.

```text
              FRONTEND DEVELOPMENT
                       |
          ┌────────────┼────────────┐
          ↓            ↓            ↓
        HTML          CSS      JavaScript
          |            |            |
          ↓            ↓            ↓
      Structure      Style       Behavior
```

For example, consider a simple button.

HTML creates the button:

```html
<button>Click Me</button>
```

CSS can control how the button looks:

```css
button {
  background-color: blue;
  color: white;
  padding: 10px 20px;
  border-radius: 6px;
}
```

JavaScript can control what happens when the button is clicked:

```javascript
button.addEventListener("click", () => {
  alert("Button clicked!");
});
```

---

# Introduction to Frontend Development

**Frontend development** is the development of the part of a website or web application that users directly see and interact with. It focuses primarily on the **client side** of a web application—the part that runs in the user's browser. It includes things such as:

- Page structure
- Layout
- Colors
- Typography
- Images
- Buttons
- Forms
- Navigation
- Animations
- User interactions
- Responsive design

A simplified frontend can be represented as:

```text
                 FRONTEND
                    |
        ┌───────────┼───────────┐
        ↓           ↓           ↓
      HTML         CSS      JavaScript
        |           |           |
        ↓           ↓           ↓
   Structure      Styling    Behavior
```

---

## HTML — Structure

**HTML** stands for **HyperText Markup Language**. HTML is used to define the **structure and content** of a webpage.

Example:

```html
<h1>My Portfolio</h1>

<p>Welcome to my portfolio.</p>

<button>Contact Me</button>
```

HTML tells the browser:

```text
There is a heading.
There is a paragraph.
There is a button.
```

It does not primarily describe how those elements should visually appear. Think of HTML as the **skeleton or structure** of a webpage.

---

# CSS — Presentation

**CSS** stands for **Cascading Style Sheets**. CSS is used to control the **presentation, appearance, and layout** of HTML elements.

Example:

```css
h1 {
  color: darkblue;
  font-size: 40px;
}

p {
  color: gray;
}

button {
  background-color: black;
  color: white;
}
```

CSS can control many aspects of a webpage, including:

- Colors
- Fonts
- Text size
- Spacing
- Borders
- Backgrounds
- Width and height
- Positioning
- Layout
- Responsive behavior
- Transitions
- Animations

---

# JavaScript — Behavior

**JavaScript** is a programming language commonly used to add **behavior and interactivity** to web pages.

For example, JavaScript can:

- Respond to button clicks
- Validate forms
- Change page content
- Fetch data from APIs
- Open and close menus
- Create interactive components
- Communicate with backend services

Example:

```javascript
const button = document.querySelector("button");

button.addEventListener("click", () => {
  alert("Hello!");
});
```

---

# HTML, CSS and JavaScript Together

Consider a login form.

### HTML

HTML creates the structure:

```html
<form>
  <label>Email</label>
  <input type="email" />

  <label>Password</label>
  <input type="password" />

  <button>Login</button>
</form>
```

### CSS

CSS styles the form:

```css
form {
  width: 300px;
  padding: 20px;
}

input {
  padding: 10px;
}

button {
  padding: 10px 20px;
}
```

### JavaScript

JavaScript can add behavior:

```javascript
form.addEventListener("submit", (event) => {
  event.preventDefault();

  console.log("Form submitted");
});
```

---

# Quick Summary

| Technology     | Main Responsibility               |
| -------------- | --------------------------------- |
| **HTML**       | Structure and content             |
| **CSS**        | Presentation, styling and layout  |
| **JavaScript** | Behavior, logic and interactivity |

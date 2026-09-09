# Frontend Development

HTML doesn't exist by itself in modern frontend development. A typical frontend is built around **three fundamental technologies**:

```text
                FRONTEND
                   │
        ┌──────────┼──────────┐
        │          │          │
        ▼          ▼          ▼
       HTML       CSS    JavaScript
        │          │          │
        ▼          ▼          ▼
    Structure   Styling    Behaviour
```

---

## HTML — Structure

HTML describes **what is on the webpage**.

For example:

```html
<h1>My Portfolio</h1>

<p>Welcome to my portfolio.</p>

<button>Contact Me</button>
```

HTML tells the browser:

> There is a heading, a paragraph, and a button.

---

## CSS — Presentation

CSS stands for **Cascading Style Sheets**. CSS controls how HTML content **looks**.

CSS is responsible for things such as:

- Colors
- Fonts
- Spacing
- Sizes
- Layouts
- Borders
- Animations
- Responsive design

For example:

```css
h1 {
  color: blue;
  font-size: 40px;
}
```

---

## JavaScript — Behaviour

JavaScript adds **behaviour and interactivity** to a webpage.

For example:

```javascript
const button = document.querySelector("#helloBtn");

button.addEventListener("click", () => {
  alert("Hello!");
});
```

---

## ⚠️ Important Distinction

HTML, CSS, and JavaScript are **not three competing ways of doing the same thing**.

They solve **different problems**.

| Technology     | Main Responsibility       |
| -------------- | ------------------------- |
| **HTML**       | Structure & meaning       |
| **CSS**        | Presentation & layout     |
| **JavaScript** | Behaviour & interactivity |

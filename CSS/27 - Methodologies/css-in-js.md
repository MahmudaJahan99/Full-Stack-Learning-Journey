# CSS-in-JS

**CSS-in-JS** is an approach where CSS styles are written and managed using JavaScript. It became especially popular in component-based JavaScript applications. CSS-in-JS can provide features such as:

- Component-level styling
- Dynamic styles
- Local style management
- JavaScript-based values
- Colocation of styles and components

Instead of having:

```text
Component.jsx
Component.css
```

styles can be defined alongside JavaScript:

```jsx
const buttonStyle = {
  backgroundColor: "blue",
  color: "white",
  padding: "10px 20px",
};
```

Then:

```jsx
<button style={buttonStyle}>Submit</button>
```

This particular example uses React's inline `style` object. More broadly, **CSS-in-JS** refers to libraries and approaches that generate/manage CSS through JavaScript rather than simply using React's built-in inline style object.

## CSS-in-JS Libraries

Examples historically associated with CSS-in-JS include **styled-components** and **Emotion**.

The exact choice depends on the project's architecture and requirements.

A styled-components-style example looks conceptually like:

```jsx
const Button = styled.button`
  background: blue;
  color: white;
  padding: 10px 20px;
`;
```

Then:

```
<Button>Submit</Button>
```

The styling is defined alongside the component.

# CSS Modules

**CSS Modules** is a CSS approach where styles are locally scoped to a component/module. It is commonly used with JavaScript frameworks such as React.

Normally, a CSS class can potentially have global scope. Another component could accidentally use the same class name. CSS Modules solve this by making class names **locally scoped**.

Suppose we have:

```text
Button.module.css
```

Inside:

```css
.button {
  background-color: blue;
  color: white;
}
```

A React component can import it:

```jsx
import styles from "./Button.module.css";

function Button() {
  return <button className={styles.button}>Submit</button>;
}
```

The bundler generates a unique class name for the CSS module.

Conceptually:

```text
.button
   ↓
unique generated class name
   ↓
Button_button__abc123
```

The exact generated name depends on the tooling.

```text
Component
    │
    ▼
Component.module.css
    │
    ▼
Local CSS
    │
    ▼
Build Tool
    │
    ▼
Unique class names
```

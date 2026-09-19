# CSS Methodologies

As a project grows, CSS can become difficult to manage. But a large application can have hundreds or thousands of styles. At that point, developers need better ways to:

- Organize CSS
- Reuse styles
- Avoid naming conflicts
- Manage large stylesheets
- Share design patterns
- Scope styles to components
- Extend CSS with additional features
- Keep styles maintainable

This is where **CSS methodologies and tools** become useful.

## CSS Methodologies & Tools

The roadmap includes:

```text
                 CSS Methodologies
                         │
       ┌─────────────────┼──────────────────┐
       │                 │                  │
    Preprocessor       Tooling          Methodologies
       │                 │                  │
      Sass            PostCSS          BEM
                                         │
                                  Component Styling
                                    │          │
                              CSS Modules   CSS-in-JS
```

These technologies do **different jobs**.

| Technology      | Main Idea                                      |
| --------------- | ---------------------------------------------- |
| **Sass**        | Extends CSS with additional authoring features |
| **PostCSS**     | Processes CSS using plugins                    |
| **BEM**         | Naming methodology for organizing CSS classes  |
| **CSS Modules** | Locally scopes CSS to components/modules       |
| **CSS-in-JS**   | Writes/manages styles using JavaScript         |

---

## A Simple Comparison

```text
                 CSS
                  │
        ┌─────────┼──────────┐
        │         │          │
        ▼         ▼          ▼
      Sass      PostCSS     BEM
        │         │          │
    Authoring  Processing  Naming
        │         │          │
        └─────────┼──────────┘
                  │
          Component Styling
                  │
             ┌────┴────┐
             │         │
             ▼         ▼
       CSS Modules   CSS-in-JS
          Scoping      JS-based
                       styling
```

> **Sass extends how you write CSS, PostCSS processes CSS, BEM organizes class names, CSS Modules scopes styles, and CSS-in-JS manages styles through JavaScript.**

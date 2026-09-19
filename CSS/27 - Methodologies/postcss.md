# PostCSS

**PostCSS** is a tool for transforming CSS using JavaScript-based plugins. The basic idea is:

```text
CSS
 ↓
PostCSS
 ↓
Plugins
 ↓
Processed CSS
```

PostCSS itself is not simply "a collection of CSS features." It provides a system that allows plugins to **parse and transform CSS**.

Different plugins can perform different tasks.

For example:

```text
                 PostCSS
                    │
       ┌────────────┼────────────┐
       │            │            │
       ▼            ▼            ▼
   Autoprefixer   Minifier    Custom Plugin
       │            │            │
       ▼            ▼            ▼
Browser          Smaller      Custom
compatibility    CSS          transformation
```

## Autoprefixer

One commonly used PostCSS plugin is **Autoprefixer**.

Suppose we write:

```css
.example {
  display: flex;
}
```

A build tool using Autoprefixer can add browser-specific prefixes when necessary based on the configured browser targets. We generally don't want to manually add every vendor prefix yourself.

Conceptually:

```text
CSS
   ↓
Autoprefixer
   ↓
Browser-compatible CSS
```

### Autoprefixer with SCSS

```text
SCSS
 ↓
Sass
 ↓
CSS
 ↓
PostCSS plugins
 ↓
Final CSS
```

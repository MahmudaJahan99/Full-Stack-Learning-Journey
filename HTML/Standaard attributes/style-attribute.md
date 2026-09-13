# `style`

The `style` attribute allows you to apply **CSS directly to an individual HTML element**. This is called **inline CSS**.

```html
<p style="color: blue;">Hello World!</p>
```

The HTML element contains both content and styling information.

---

## Multiple CSS Properties

You can place multiple CSS declarations inside `style`. Each declaration is separated by a semicolon.

```html
<p style="color: blue; font-size: 20px;">Hello World!</p>
```

---

### Why Is Inline CSS Usually Not Preferred?

Although `style` is useful, generally large amounts of CSS directly inside HTML is not preferred.

For example:

```html
<div
  style="
        background: black;
        color: white;
        padding: 20px;
        margin: 20px;
        border-radius: 10px;
    "
>
  Hello
</div>
```

Imagine doing this for 50 elements. Your HTML would become difficult to maintain.

A better approach is usually separated styling from the HTML structure.

```html
<div class="card">Hello</div>
```

and then:

```css
.card {
  background: black;
  color: white;
  padding: 20px;
  margin: 20px;
  border-radius: 10px;
}
```

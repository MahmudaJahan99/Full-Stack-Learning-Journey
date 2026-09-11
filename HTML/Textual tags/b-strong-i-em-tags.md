# Text Formatting & Emphasis

HTML provides several elements for giving text **meaning or emphasis**.

---

## `<b>` — Bold Text

`<b>` draws attention to text without giving it additional importance or emphasis.

```html
<p>This is <b>bold text</b>.</p>
```

Visually:

```text
This is BOLD TEXT.
        ↑
       <b>
```

---

## `<strong>` — Strong Importance

`<strong>` indicates that the content has strong importance, seriousness, or urgency. Browsers normally display it in bold.

```html
<p><strong>Warning:</strong> Do not delete this file.</p>
```

```text
Warning: Do not delete this file.
^^^^^^^^
 strong
```

---

### `<b>` vs `<strong>`

```text
<b>
 │
 └── "Pay attention to this visually."

<strong>
 │
 └── "This content is important."
```

Example:

```html
<p>The package is <b>blue</b>.</p>

<p>
  <strong>Do not open this package.</strong>
</p>
```

---

## `<i>` — Italic Text

`<i>` represents text that is set apart from the surrounding content. Browsers normally display it in italic.

```html
<p>This is <i>italic text</i>.</p>
```

It can be useful for things such as:

- Alternative voice
- Technical terms
- Foreign words
- Names/designations in certain contexts

---

## `<em>` — Emphasized Text

`<em>` represents emphasis. Browsers normally display `<em>` as italic. But the important difference is **meaning**.

```html
<p>I <em>really</em> want to learn JavaScript.</p>
```

---

### `<i>` vs `<em>`

```text
<i>
 │
 └── Different/set-apart text


<em>
 │
 └── Emphasized text
```

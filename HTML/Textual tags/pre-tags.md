# `<pre>` — Preformatted Text

`<pre>` displays text while preserving its whitespace and line breaks. Normally, HTML collapses consecutive spaces and line breaks. The browser generally renders the extra spaces as a single space.

But:

```html
<pre>
Hello       World
    This indentation
        is preserved.
</pre>
```

## Useful for

- Code snippets
- ASCII art
- Text where whitespace matters
- Preformatted output

Example:

```html
<pre>
   /\_/\
  ( o.o )
   > ^ <
</pre>
```

Result:

```text
   /\_/\
  ( o.o )
   > ^ <
```

### `<pre>` and code

For displaying source code, `<pre>` is often combined with `<code>`:

```html
<pre>
    <code>
        const name = "Mahmuda";
        console.log(name);
    </code>
</pre>
```

Here:

- `<code>` says "this is code"
- `<pre>` preserves the formatting

---

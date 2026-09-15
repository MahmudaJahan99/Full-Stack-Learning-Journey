# HTML — Embedding Media

Modern websites rarely contain only text. Moder website commonly need to embed.

- Images
- Audio
- Videos
- Maps
- YouTube videos
- Other webpages
- Interactive content

HTML provides several elements specifically designed for embedding this type of content.

```text
                 Embedding Media
                       │
       ┌───────────────┼────────────────┐
       ↓               ↓                ↓
     Audio           Video            Images
       │               │                │
       │               │          ┌─────┴─────┐
       │               │          ↓           ↓
       │               │        img        figure
       │               │
       └───────────────┴────── iframe
                              │
                              ↓
                             CSP
```

---

## What Does "Embedding Media" Mean?

**Embedding media** means placing external or multimedia content inside an HTML document so that it can be displayed or played as part of a webpage. The image file is not HTML itself.

```html
<img src="cat.jpg" alt="A sleeping cat" />
<audio src="song.mp3" controls></audio>
<iframe src="https://example.com"></iframe>
```

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

---

# 31. A Practical Image Example

Imagine a product page:

```html
<img src="product-hero.jpg" alt="Black leather handbag" fetchpriority="high" />

<img
  src="product-side.jpg"
  alt="Side view of black leather handbag"
  loading="lazy"
/>

<img
  src="related-product.jpg"
  alt="Brown leather wallet"
  loading="lazy"
  fetchpriority="low"
/>
```

The idea is:

```text
Main product image
        ↓
     IMPORTANT
        ↓
 fetchpriority="high"


Images farther down page
        ↓
     LESS URGENT
        ↓
 loading="lazy"
```

---

# 32. Putting Everything Together

Here's a small webpage using several concepts from this topic:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Media Example</title>
  </head>

  <body>
    <h1>My Media Page</h1>

    <!-- Image -->
    <img
      src="hero.jpg"
      alt="A beautiful mountain landscape"
      fetchpriority="high"
    />

    <!-- Figure -->
    <figure>
      <img src="sales-chart.png" alt="Sales increased from January to June" />

      <figcaption>Sales growth during the first half of the year.</figcaption>
    </figure>

    <!-- Audio -->
    <h2>Podcast</h2>

    <audio controls>
      <source src="podcast.mp3" type="audio/mpeg" />
      Your browser does not support the audio element.
    </audio>

    <!-- Video -->
    <h2>Introduction Video</h2>

    <video controls poster="video-thumbnail.jpg">
      <source src="intro.mp4" type="video/mp4" />

      <track src="captions.vtt" kind="captions" srclang="en" label="English" />

      Your browser does not support the video element.
    </video>

    <!-- iframe -->
    <h2>Location</h2>

    <iframe src="map.html" title="Map showing our location" loading="lazy">
    </iframe>
  </body>
</html>
```

---

# 33. The Big Mental Model

When embedding media, ask:

```text
What am I embedding?
        │
        ├── Sound?
        │     └── <audio>
        │
        ├── Video?
        │     └── <video>
        │
        ├── Image?
        │     ├── <img>
        │     └── <figure> + <figcaption>
        │
        └── External content?
              └── <iframe>
```

Then ask:

```text
             Media
               │
       ┌───────┼────────┐
       ↓       ↓        ↓
    Meaning  Security  Performance
       │       │        │
       ↓       ↓        ↓
    alt     CSP       loading
    caption sandbox    fetchpriority
    track
```

This is the real purpose of this roadmap section.

---

# 34. Common Mistakes

### ❌ Missing `alt`

```html
<img src="cat.jpg" />
```

Better:

```html
<img src="cat.jpg" alt="Sleeping cat" />
```

---

### ❌ Using `alt="image"`

```html
<img src="chart.png" alt="image" />
```

This doesn't communicate what the image means.

Better:

```html
<img src="chart.png" alt="Monthly sales increased by 25 percent" />
```

---

### ❌ Using `<figure>` for every image

You don't need:

```html
<figure>
  <img src="logo.png" alt="Company logo" />
</figure>
```

for every image.

Use `<figure>` when the image forms a meaningful, self-contained piece of content, particularly when a caption or associated content is useful.

---

### ❌ Using iframe without a title

Avoid:

```html
<iframe src="map.html"></iframe>
```

Prefer:

```html
<iframe src="map.html" title="Map showing our office location"> </iframe>
```

---

### ❌ Making everything high priority

Don't do this:

```html
<img fetchpriority="high" src="image1.jpg" />
<img fetchpriority="high" src="image2.jpg" />
<img fetchpriority="high" src="image3.jpg" />
<img fetchpriority="high" src="image4.jpg" />
<img fetchpriority="high" src="image5.jpg" />
```

Priority is useful because **not everything has the same importance**.

---

### ❌ Using autoplay carelessly

Unexpected sound can create a poor user experience and autoplay policies may prevent it.

Be especially careful with:

```html
<audio autoplay></audio>
```

and:

```html
<video autoplay></video>
```

---

# 35. Quick Reference

| Element / Attribute | Purpose                                      |
| ------------------- | -------------------------------------------- |
| `<audio>`           | Embeds audio                                 |
| `<video>`           | Embeds video                                 |
| `<source>`          | Provides media source alternatives           |
| `<track>`           | Adds captions/subtitles and other timed text |
| `<iframe>`          | Embeds external content                      |
| `<img>`             | Embeds an image                              |
| `<figure>`          | Represents self-contained content            |
| `<figcaption>`      | Caption for a figure                         |
| `src`               | Resource URL                                 |
| `alt`               | Alternative text for an image                |
| `poster`            | Video preview image                          |
| `loading="lazy"`    | Defers loading when appropriate              |
| `fetchpriority`     | Communicates resource priority               |
| `CSP`               | Controls allowed resource/content sources    |
| `sandbox`           | Restricts iframe capabilities                |

---

# 36. Things to Remember

### Audio

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg" />
</audio>
```

### Video

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
</video>
```

### Image

```html
<img src="photo.jpg" alt="Description" />
```

### Figure

```html
<figure>
  <img src="chart.png" alt="Description of chart" />
  <figcaption>Sales during 2026.</figcaption>
</figure>
```

### iframe

```html
<iframe src="..." title="Description of embedded content"> </iframe>
```

### Priority

```html
<img src="hero.jpg" alt="..." fetchpriority="high" />
```

### Lazy loading

```html
<img src="photo.jpg" alt="..." loading="lazy" />
```

---

# 37. Mini Practice

## 🟢 Easy

Create a page containing:

1. One image
2. One audio player
3. One video player

Give the image meaningful `alt` text and add `controls` to the audio/video.

---

## 🟡 Intermediate

Create a product page containing:

- A hero product image
- Three additional product images
- A product description
- A product demonstration video

Requirements:

- Use meaningful `alt` text.
- Give the hero image `fetchpriority="high"`.
- Lazy-load images that aren't immediately important.
- Add a `poster` to the video.

---

## 🔴 Deep Dive

Create an article page containing:

```text
Article
  │
  ├── Hero image
  │
  ├── Figure + caption
  │
  ├── Embedded video
  │     └── captions
  │
  ├── Audio interview
  │
  └── Embedded map using iframe
```

Then think about:

1. Which resources should load immediately?
2. Which resources can be lazy-loaded?
3. Which images are decorative?
4. Which images need meaningful `alt` text?
5. Which content deserves `<figure>`?
6. What iframe permissions/security restrictions might be appropriate?
7. What could CSP restrict?

---

# 38. The Bigger Picture

This topic introduces an important transition from **basic HTML structure** to real-world web development.

You're no longer just writing:

```html
<h1>Hello</h1>
<p>Hello world!</p>
```

You're now dealing with:

```text
                  Web Page
                     │
       ┌─────────────┼─────────────┐
       ↓             ↓             ↓
     Content       Media        External
       │             │           Content
       ↓             ↓             ↓
    headings      images       iframes
    paragraphs    audio        embeds
    lists         video
                  │
                  ↓
          ┌───────────────┐
          │               │
      Accessibility   Performance
          │               │
       alt/track      lazy loading
       captions       priority
          │               │
          └───────┬───────┘
                  ↓
              Security
                  │
                  ↓
                 CSP
```

The important mindset is:

> **Embedding media isn't just about displaying something. It's about choosing the correct semantic element, making it accessible, loading it efficiently, and considering security.**

That mindset will become increasingly important as you move from HTML into **CSS, JavaScript, React, performance, accessibility, and full-stack development**.

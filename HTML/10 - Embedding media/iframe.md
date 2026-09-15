# iframe

`<iframe>` stands for **Inline Frame**. It allows another webpage or embeddable document/content to appear inside your webpage.

Example:

```html
<iframe src="https://example.com" title="Example website"> </iframe>
```

Conceptually:

```text
webpage
┌─────────────────────────────────────┐
│                                     │
│   HTML                              │
│                                     │
│  ┌───────────────────────────────┐  │
│  │       Embedded content        │  │
│  │                               │  │
│  │       <iframe>                │  │
│  │                               │  │
│  └───────────────────────────────┘  │
│                                     │
└─────────────────────────────────────┘
```

## Common Uses of `<iframe>`

iframes are required when embedding:

- YouTube videos
- Google Maps
- online documents
- forms
- dashboards
- external applications
- other embeddable content

For example, a video platform may provide an iframe embed code.

```html
<iframe src="https://www.youtube.com/embed/example" title="Video"> </iframe>
```

The exact URL and permissions depend on the service.

## Important iframe Attributes

1. `src` - Specifies what should be embedded.
2. `title` - Provides an accessible description of the iframe.
3. `width` and `height` - Specifies the dimensions.
4. `loading` - Controls when the iframe should be loaded. `lazy` can delay loading until the iframe is near the user's viewport. This can help performance when the iframe is far down the page.
5. `allow` - Controls certain capabilities available to embedded content.
6. `sandbox` - Adds restrictions to content inside the iframe. Specific capabilities can be selectively allowed.

```html
<iframe
  src="map.html"
  title="Map showing our office location"
  width="600"
  height="400"
  loading="lazy"
>
</iframe>

<iframe src="external.html" sandbox title="External content"> </iframe>
```

## iframe Security

An iframe can load content from another origin. That means we should think carefully about:

- what is embeded
- where it comes from
- what permissions it receives
- what security policies apply

Never assume that embedding something means it is automatically safe.

# CSP — Content Security Policy

CSP stands for **Content Security Policy**. CSP is a browser security mechanism that allows a website to specify which sources are allowed for different kinds of content. It helps reduce certain attacks, particularly **Cross-Site Scripting (XSS)** and unwanted resource loading.

Think of CSP as a security rulebook:

```text
             CSP
              │
       "Which sources
       are allowed?"
              │
     ┌────────┼─────────┐
     ↓        ↓         ↓
  Scripts   Images    Frames
     │        │         │
  allowed?  allowed?  allowed?
```

## Basic CSP Example

A CSP can be sent using an HTTP response header such as:

```http
Content-Security-Policy: default-src 'self'
```

This basically establishes a restrictive default policy where resources are generally expected to come from the same origin. A policy can be more specific.

Example:

```http
Content-Security-Policy:
    default-src 'self';
    img-src 'self' https://images.example.com;
```

This says, conceptually:

```text
Everything → same origin by default

Images → same origin
          OR
          images.example.com
```

---

## CSP and iframes

CSP has directives that can control embedded content.

Example:

```http
frame-src https://www.youtube.com;
```

This can specify which sources a page is allowed to load in frames. So CSP becomes especially relevant when a website embeds external content.

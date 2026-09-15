# Accessibility

**Web accessibility** means designing and developing websites so that they can be used by as many people as possible, including people with disabilities. The goal is to make the web **usable, understandable, and navigable for everyone**. Accessibility considers people who may have:

- Visual disabilities
- Hearing disabilities
- Motor disabilities
- Cognitive disabilities
- Temporary or situational limitations

## Why Accessibility Matters

A website should not depend only on the user's ability to:

- See every visual element
- Use a mouse
- Hear audio
- Understand complex interactions

For example, someone may navigate a website entirely using a **keyboard** or a **screen reader**.

Good accessibility makes the website more inclusive and often improves the experience for everyone.

---

### Semantic HTML

Using the correct HTML elements gives browsers and assistive technologies meaningful information about the page.

Instead of:

```html
<div onclick="submitForm()">Submit</div>
```

Use:

```html
<button onclick="submitForm()">Submit</button>
```

A `<button>` already communicates that the element is interactive.

**Common semantic elements**

```html
</header><header>
</nav><nav>
</main><main>
<section></section>
<article></article>
<aside></aside>
<footer></footer>
<button></button>
<form></form>
<label></label>
```

Semantic HTML should generally be preferred over using generic `<div>` elements for everything.

### Alternative Text

Screen readers can read the alternative text to users who cannot see the image. Images should have meaningful `alt` text when the image communicates information.

```html
<img src="profile.jpg" alt="A woman standing in a garden" />
```

This tells assistive technologies that the image does not provide useful information. If an image is purely decorative, it can use an empty `alt` attribute.

```html
<img src="decoration.png" alt="" />
```

### Accessible Forms

Form controls should have associated labels.

```html
<label for="email"> Email </label>

<input type="email" id="email" />
```

The `for` attribute connects the label to the input's `id`. This makes the form easier to understand and interact with, especially for screen-reader and keyboard users.

### Keyboard Accessibility

Users should be able to navigate and operate important parts of a website using a keyboard.

For example:

```text
Tab → Move between interactive elements
Enter → Activate certain controls
Space → Activate buttons/controls
Arrow keys → Navigate some widgets
```

Avoid creating interactions that can only be performed with a mouse.

### Color and Contrast

Do not use color as the **only way** to communicate information.

Bad:

```text
Red = Error
Green = Success
```

Someone with certain color-vision deficiencies may not be able to distinguish them.

Better:

```text
❌ Error: Invalid email address

✓ Success: Email address accepted
```

Text should also have sufficient contrast against its background.

### Headings

Headings provide structure to a page. Use headings in a meaningful hierarchy.

```html
<h1>My Portfolio</h1>

<h2>Projects</h2>

<h3>Project One</h3>

<h3>Project Two</h3>

<h2>Contact</h2>
```

Headings help users understand the structure of the page and allow assistive-technology users to navigate between sections.

### Links Should Be Meaningful

Link text should communicate where the link leads. Meaningful link text provides useful context even when the surrounding content is not read.

Avoid:

```html
<a href="/projects">Click here</a>
```

Prefer:

```html
<a href="/projects">View my projects</a>
```

---

## ARIA

**ARIA** stands for **Accessible Rich Internet Applications**. ARIA provides additional attributes that can communicate information about custom interfaces to assistive technologies.

Example:

```html
<button aria-label="Close">×</button>
```

### Accessibility and Responsive Design

Accessibility is not limited to screen readers. A responsive and accessible interface should remain usable rather than simply becoming visually smaller. A website should also work well across:

- Different screen sizes
- Different input methods
- Different browsers
- Different devices
- Different user preferences

---

### Accessibility Checklist

Before considering a page accessible, check:

- ✓ Semantic HTML is used
- ✓ Images have appropriate `alt` text
- ✓ Forms have labels
- ✓ Interactive elements work with a keyboard
- ✓ Links have meaningful text
- ✓ Heading hierarchy is logical
- ✓ Color is not the only way to communicate information
- ✓ Text has sufficient contrast
- ✓ Custom components provide appropriate accessibility information

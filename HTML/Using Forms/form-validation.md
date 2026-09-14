# Form Validation

Validation means checking whether the information entered by the user is acceptable. Validation can happen at multiple levels:

```text
User input
    │
    ↓
Browser validation
    │
    ↓
JavaScript validation
    │
    ↓
Server-side validation
```

---

## `required`

The simplest validation attribute is **required**

```html
<input type="text" name="username" required />
```

The user must provide a value before the form can normally be submitted.

## `minlength` and `maxlength`

Controls text length.

```html
<input type="text" name="username" minlength="3" maxlength="20" />
<textarea name="message" minlength="10" maxlength="500"></textarea>
```

## `min` and `max`

For numerical values the browser can check that the value falls within the specified range.

```html
<input type="number" name="age" min="18" max="100" />
```

## `pattern`

The `pattern` attribute allows a regular expression to define an expected format. This requires the value to follow the specified pattern.

```html
<input type="text" name="username" pattern="[A-Za-z0-9]+" />
<input type="text" name="code" pattern="[A-Z]{3}[0-9]{3}" />
```

Pattern validation can be powerful, but regular expressions can also become difficult to read.

---

## Client-Side vs Server-Side Validation

### Client-side validation

Happens in the browser. But it is **not trustworthy for security**.

Examples:

```html
required minlength maxlength pattern min max type="email"
```

Advantages:

- Immediate feedback
- Better user experience
- Reduces unnecessary requests
- Easy for users to understand

### Server-side validation

Happens on the server. The server must validate submitted data independently. Because a user can bypass browser validation.

For example, someone could:

- Disable JavaScript
- Modify the HTML
- Send requests directly
- Use developer tools
- Write their own HTTP request

---

## The `novalidate` Attribute

A form can disable the browser's built-in validation. This is sometimes useful when JavaScript is responsible for custom validation behavior.

```html
<form novalidate>...</form>
```

However, disabling native validation means we need to make sure our own validation system properly handles all necessary checks.

# Labels and Inputs

A label tells the user **what an input is for**. A label isn't just text placed beside an input. It creates a semantic relationship between the description and the form control. This improves:

- Accessibility
- Screen-reader support
- Usability
- Click/tap behavior

Example:

```html
<label for="email">Email address:</label>

<input type="email" id="email" name="email" />
```

Visual idea:

```text
Email address:
┌─────────────────────────────┐
│                             │
└─────────────────────────────┘
```

---

## Connecting `<label>` and `<input>`

```html
<label for="username">Username:</label>

<input type="text" id="username" name="username" />
```

Notice:

```text
<label for="username">
             │
             │ matches
             ↓
<input id="username">
```

This connects the label to the input.

Another way to associate a label is An by placing an input inside its label.

```html
<label>
  Username:
  <input type="text" name="username" />
</label>
```

---

### The `name` Attribute

`id` and `name` have different jobs.

```text
id
 ↓
Identifies the element in the document

name
 ↓
Identifies the submitted form field
```

Example:

```html
<input type="text" id="username" name="username" />
<input type="email" id="email" name="email" />
```

When the form is submitted, the backend can receive something conceptually like:

```text
email = "jane@example.com"
```

Without a meaningful `name`, the value generally won't be included in the normal form data submission.

---

### Common Input Types

The `<input>` element can represent many different controls. The `type` attribute tells the browser what kind of input control it should provide.

1. Text - This is appropriate for ordinary text.

```html
<input type="text" />
```

2. Email - The browser knows that the field is intended for an email address. This allows browsers to provide appropriate validation and mobile keyboards.

```html
<input type="email" />
```

3. Password - The browser hides the entered characters.

```html
<input type="password" />
```

4. Number - Can have constraints.

```html
<input type="number" id="age" name="age" min="18" max="100" />
```

5. Date

```html
<input type="date" />
```

6. Time

```html
<input type="time" />
```

7. Search

```html
<input type="search" />
```

8. URL

```html
<input type="url" />
```

9. Telephone

```html
<input type="tel" />
```

10. Checkbox - Checkboxes are useful when the user can select **zero or more options**.

```html
<label>
  <input type="checkbox" name="skills" value="html" />

  HTML
</label>

<label>
  <input type="checkbox" name="skills" value="css" />

  CSS
</label>

<label>
  <input type="checkbox" name="skills" value="javascript" />

  JavaScript
</label>
```

11. Radio button - Used when the user should select **one option from a group**. The important part is that they share the same `name`

```html
<p>Experience level:</p>

<label>
  <input type="radio" name="experience" value="beginner" />
  Beginner
</label>

<label>
  <input type="radio" name="experience" value="intermediate" />
  Intermediate
</label>

<label>
  <input type="radio" name="experience" value="advanced" />
  Advanced
</label>
```

12. File - HTML forms can allow users to upload files.

```html
<label for="resume">Upload your resume:</label>

<input
  type="file"
  id="resume"
  name="resume"
  accept=".pdf,.doc,.docx"
  multiple
/>
```

13. Select Dropdowns - Forms can also use `<select>`.

```html
<label for="country">Country:</label>

<select id="country" name="country">
  <option value="bd">Bangladesh</option>
  <option value="in">India</option>
  <option value="us">United States</option>
</select>
```

14. Textarea - used for longer text.

```html
<label for="message">Message:</label>

<textarea id="message" name="message"></textarea>
```

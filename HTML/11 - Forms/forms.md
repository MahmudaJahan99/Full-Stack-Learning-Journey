# Forms

Forms are used when a webpage needs to **collect information from a user**. Examples include:

- Login forms
- Registration forms
- Search boxes
- Contact forms
- Checkout forms
- Feedback forms
- Job applications
- File uploads
- Surveys
- Payment information
- Customer complaint forms

A form creates a bridge between:

```text
User
  │
  │ enters information
  ↓
HTML Form
  │
  │ submits data
  ↓
Server / Backend
  │
  ↓
Database / Application
```

HTML provides the **structure and basic browser behavior** of the form. JavaScript can add **dynamic behavior and advanced validation**. The backend is responsible for **processing and securely validating submitted data**.

---

## The `<form>` Element

The `<form>` element represents a section of a webpage that contains controls for submitting information.

```html
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" />

  <button type="submit">Submit</button>
</form>
```

### `action`

The `action` attribute specifies **where the submitted form data should be sent**.

Example:

```html
<form action="/submit">...</form>
```

When the form is submitted, the browser sends the form data to:

```text
/submit
```

### `method`

The `method` attribute determines how the browser submits the form data.

Common methods are:

```html
<form action="/search" method="get">...</form>
```

and:

```html
<form action="/register" method="post">...</form>
```

---

### GET vs POST

#### GET

GET places form data into the URL.

Example:

```text
/search?query=html
```

This makes GET useful for things such as:

- Search
- Filtering
- Queries
- Pages that can be bookmarked/shared

Example:

```html
<form action="/search" method="get">
  <label for="query">Search:</label>
  <input type="search" id="query" name="query" />

  <button type="submit">Search</button>
</form>
```

---

#### POST

POST sends the form data as part of the request rather than putting the values in the URL.

It is commonly used for operations such as:

- Registration
- Login
- Creating records
- Updating data
- Uploading files

Example:

```html
<form action="/register" method="post">...</form>
```

---

## Limitations of HTML Forms

1. HTML doesn't process form data
2. Native Validation Is Basic
3. Browser Validation Can Be Bypassed
4. Styling Native Controls Can Differ
5. HTML Doesn't Automatically Store Data

---

## `<fieldset>` and `<legend>`

For related groups of controls, HTML provides `<fieldset></fieldset>`

Example:

```html
<form>
  <fieldset>
    <legend>Personal Information</legend>

    <label for="name">Name:</label>
    <input type="text" id="name" name="name" />

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" />
  </fieldset>

  <button type="submit">Submit</button>
</form>
```

---

## `<button>`

A form commonly contains a submit button and the `type` matters.

```html
<button type="submit">Submit</button>
```

Common button types:

- submit --> Submits the form.
- reset --> Resets controls to their initial values.
- button --> A normal button that doesn't submit the form by default. This becomes especially useful when JavaScript is involved.

---

## Important Form Attributes

| Attribute      | Purpose                                                                       |
| -------------- | ----------------------------------------------------------------------------- |
| `action`       | Where form data is submitted                                                  |
| `method`       | How data is submitted                                                         |
| `name`         | Name of submitted form field                                                  |
| `id`           | Identifies an element                                                         |
| `required`     | Value must be provided                                                        |
| `placeholder`  | Shows an input hint                                                           |
| `minlength`    | Minimum text length                                                           |
| `maxlength`    | Maximum text length                                                           |
| `min`          | Minimum numeric/date value                                                    |
| `max`          | Maximum numeric/date value                                                    |
| `pattern`      | Regular-expression constraint                                                 |
| `accept`       | Suggested file types                                                          |
| `multiple`     | Allows multiple selections/files                                              |
| `enctype`      | Specifies form-data encoding                                                  |
| `autocomplete` | Gives browser autocomplete hints                                              |
| `disabled`     | Disables a control                                                            |
| `readonly`     | Prevents editing while remaining usable for submission in applicable controls |
| `checked`      | Initially selects checkbox/radio                                              |
| `selected`     | Initially selects an option                                                   |

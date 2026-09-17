# CSS — Attribute Selectors

> **Attribute selectors** allow us to select HTML elements based on their **attributes** or **attribute values**. With attribute selectors, CSS can target elements based on attribute information.

```html
<input type="text" />
<input type="email" />
<input type="password" />
```

Here, `type` is an **attribute** and `"text"`, `"email"`, and `"password"` are its values.

An attribute selector uses **square brackets `[]`**.

Syntax:

```css
[attribute] {
  property: value;
}
```

We can also check for a specific attribute value:

```css
[attribute="value"] {
  property: value;
}
```

Attribute selectors are useful when we want to style elements based on information already present in their HTML attributes.Common examples include:

- Styling different types of `<input>`
- Styling disabled elements
- Styling links based on their destination
- Styling links that point to specific file types
- Styling elements with particular data attributes
- Targeting elements without adding another class

---

## 1. Select Elements That Have an Attribute

The simplest attribute selector checks whether an attribute **exists**.

Syntax:

```css
[attribute] {
  property: value;
}
```

Example:

```css
[placeholder] {
  border: 1px solid black;
}

[href] {
  color: blue;
}
```

## 2. Select an Exact Attribute Value

We can select elements based on an attribute's **exact value**.

Syntax:

```css
[attribute="value"] {
  property: value;
}
```

Example:

```css
input[type="email"] {
  border: 2px solid blue;
}
```

## 3. Attribute Value Starts With

We can select elements whose attribute value **starts with a specific value**. The operator is **`^=`**.

Syntax:

```css
[attribute^="value"] {
  property: value;
}
```

Example:

```css
a[href^="https"] {
  color: green;
}
```

## 4. Attribute Value Ends With

We can select elements whose attribute value **ends with a specific value**. The operator is **`$=`**.

Syntax:

```css
[attribute$="value"] {
  property: value;
}
```

Example:

```css
a[href$=".pdf"] {
  color: red;
}
```

This selects links that end with `.pdf`.

## 5. Attribute Value Contains

We can select elements whose attribute value **contains a specific word or text**. The operator is **`*=`**

Syntax:

```css
[attribute*="value"] {
  property: value;
}
```

Example:

```css
a[href*="products"] {
  color: blue;
}
```

This selects links whose `href` contains `"products"`.

## 6. Attribute Value Is a Word

The `~=` operator selects an attribute value containing a **specific word** in a space-separated list.

Syntax:

```css
[attribute~="value"] {
  property: value;
}
```

Example:

```css
[class~="featured"] {
  border: 2px solid red;
}
```

## 7. Attribute Value Starts With a Word or Prefix

The `|=` operator is less commonly used. It selects an attribute whose value is either exactly the specified value or starts with that value followed by a hyphen.

Syntax:

```css
[attribute|="value"] {
  property: value;
}
```

Example:

```css
[lang|="en"] {
  color: blue;
}
```

This selector is particularly useful with values such as **language codes**.

---

## Attribute Selector Operators

There are several useful operators to remember:

| Selector           | Meaning                                | Example               |
| ------------------ | -------------------------------------- | --------------------- |
| `[attr]`           | Has the attribute                      | `[disabled]`          |
| `[attr="value"]`   | Exact value                            | `[type="email"]`      |
| `[attr^="value"]`  | Starts with                            | `[href^="https"]`     |
| `[attr$="value"]`  | Ends with                              | `[href$=".pdf"]`      |
| `[attr*="value"]`  | Contains                               | `[href*="products"]`  |
| `[attr~="value"]`  | Contains a whole word                  | `[class~="featured"]` |
| `[attr\|="value"]` | Exact value or starts with value + `-` | `[lang\|="en"]`       |

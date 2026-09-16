# CSS Rules

A **CSS rule** tells the browser how one or more HTML elements should be styled. A basic CSS rule looks like this:

```css
p {
  color: blue;
}
```

A CSS rule consists of a **selector** and one or more **declarations**.

```text
              CSS RULE
                  |
        ┌─────────┴─────────┐
        ↓                   ↓
    Selector           Declaration
        |                   |
        ↓             ┌─────┴─────┐
       p              ↓           ↓
                  Property       Value
                     |             |
                     ↓             ↓
                   color         blue
```

The general structure is:

```css
selector {
  property: value;
}
```

---

## Selector

A **selector** tells CSS **which HTML element or elements should be styled**. Selectors are the starting point of a CSS rule.

Example:

```css
p {
  color: blue;
}
```

Here _p_ is selector. It selects all `<p>` elements.

### Common Selectors

Some basic selectors include:

```css
/* Element selector */
p {
  color: blue;
}

/* Class selector */
.card {
  padding: 20px;
}

/* ID selector */
#header {
  background-color: black;
}

/* Universal selector */
* {
  box-sizing: border-box;
}
```

Different selectors allow to target elements in different ways.

---

## Declaration

A **declaration** tells the browser **what style should be applied** to the selected element. A declaration consists of _Property + Value_

Example:

```css
color: blue;
```

```text
Declaration
     |
 ┌───┴────┐
 ↓        ↓
Property  Value
   |        |
   ↓        ↓
 color     blue
```

The property is separated from the value using a colon `:`.

A declaration ends with a semicolon `;`.

### Declaration Block

The declarations inside `{ }` are often referred to as the **declaration block**.

```css
h1 {
  color: red;
  font-size: 32px;
}
```

The declaration block is:

```css
{
    color: red;
    font-size: 32px;
}
```

The curly braces `{ }` contain the declarations that will be applied to the selected elements.

---

## Property

A **CSS property** specifies **what aspect of an element you want to change**.

Examples include:

```text
color
background-color
font-size
width
height
margin
padding
border
display
position
```

Example:

```css
color: blue;
```

Here:

```text
color
  ↓
Property
```

---

## Value

A **value** specifies **what the property should be set to**.

Example:

```css
color: blue;
```

Here:

```text
blue
  ↓
Value
```

Different properties accept different types of values.

Example:

```css
p {
  color: red;
  font-size: 24px;
  width: 300px;
  margin: 20px;
  display: flex;
}
```

# CSS — Lists

HTML provides different types of lists for organizing related items.

CSS allows us to control how those lists **look and behave**.

For example:

```html id="h9m6gj"
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

CSS can control:

* List markers
* Numbering style
* Marker position
* List indentation
* List item spacing
* Background and borders
* Horizontal navigation lists
* Custom list designs

---

# 1. Types of HTML Lists

HTML commonly provides three types of lists:

### Unordered list

```html id="7o9t7e"
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

### Ordered list

```html id="0zqf3s"
<ol>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ol>
```

### Description list

```html id="nyz1j0"
<dl>
    <dt>HTML</dt>
    <dd>Structures the webpage.</dd>

    <dt>CSS</dt>
    <dd>Styles the webpage.</dd>
</dl>
```

CSS can style all of these differently.

---

# 2. `list-style-type`

The `list-style-type` property controls the **type of marker** displayed next to list items.

```css id="j0qv8a"
ul {
    list-style-type: square;
}
```

---

## Unordered List Markers

Common values include:

```css id="j9ik2f"
list-style-type: disc;
list-style-type: circle;
list-style-type: square;
list-style-type: none;
```

Example:

```css id="g0c8l6"
ul {
    list-style-type: square;
}
```

Result:

```text id="fj1j4k"
■ HTML
■ CSS
■ JavaScript
```

### Common unordered markers

| Value    | Marker    |
| -------- | --------- |
| `disc`   | ●         |
| `circle` | ○         |
| `square` | ■         |
| `none`   | No marker |

---

# 3. Ordered List Markers

Ordered lists can also have different numbering styles.

```css id="rj1s0j"
ol {
    list-style-type: upper-roman;
}
```

Common values include:

```css id="1xk5c4"
decimal;
decimal-leading-zero;
lower-alpha;
upper-alpha;
lower-roman;
upper-roman;
lower-latin;
upper-latin;
none;
```

For example:

```css id="sp4lpc"
ol {
    list-style-type: upper-roman;
}
```

Result:

```text id="4ljrhl"
I.   HTML
II.  CSS
III. JavaScript
```

---

# 4. `list-style-type: none`

A very common use is removing the default list markers.

```css id="l6h4ly"
ul {
    list-style-type: none;
}
```

Result:

```text id="tq1q8x"
HTML
CSS
JavaScript
```

This is particularly useful when creating:

* Navigation menus
* Sidebars
* Custom lists
* Menu components

Example:

```css id="n6wqcz"
ul {
    list-style-type: none;
    padding: 0;
}
```

---

# 5. `list-style-position`

The `list-style-position` property controls where the list marker is positioned relative to the list item's content.

There are two main values:

```css id="m5y8de"
list-style-position: outside;
list-style-position: inside;
```

---

## `outside`

This is the default behavior.

```css id="v9r4i1"
ul {
    list-style-position: outside;
}
```

Conceptually:

```text id="5b5h2p"
●  This is a list item
   with multiple lines of text.
```

The marker remains outside the main content area.

---

## `inside`

```css id="w8n6is"
ul {
    list-style-position: inside;
}
```

The marker becomes part of the list item's content area.

```text id="y8p0f9"
┌─────────────────────────────┐
│ ● This is a list item       │
│   with multiple lines.      │
└─────────────────────────────┘
```

---

# 6. `list-style-image`

You can replace the normal marker with an image.

```css id="e6qk4m"
ul {
    list-style-image: url("bullet.png");
}
```

Instead of:

```text id="h2c0u8"
● HTML
● CSS
● JavaScript
```

the browser can use the specified image as the marker.

---

# 7. `list-style`

CSS provides a shorthand property called `list-style`.

It can combine:

```text id="3m36h8"
list-style-type
list-style-position
list-style-image
```

Example:

```css id="l9k8s5"
ul {
    list-style: square inside;
}
```

This is equivalent to setting the relevant properties separately.

Another example:

```css id="c8e7bf"
ul {
    list-style: none;
}
```

This removes the default marker.

---

# 8. List Item Styling

The `<li>` element represents an individual list item.

You can style it like any other element.

```css id="s1u1ek"
li {
    margin-bottom: 10px;
}
```

HTML:

```html id="x5h4ji"
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

This creates space between the items.

```text id="b7h9d2"
● HTML

● CSS

● JavaScript
```

---

# 9. Padding and Lists

Browsers normally apply some default padding to lists.

For example:

```css id="u8xq0b"
ul {
    padding-left: 40px;
}
```

You can change it:

```css id="u1h7jg"
ul {
    padding-left: 20px;
}
```

Or remove it:

```css id="2v8c7m"
ul {
    padding-left: 0;
}
```

This is especially useful when creating custom list designs.

---

# 10. Removing Default List Styling

A common pattern for navigation menus is:

```css id="7r0m9p"
ul {
    list-style: none;
    padding: 0;
    margin: 0;
}
```

This removes the browser's default marker, padding, and margin.

HTML:

```html id="8g7y4n"
<ul>
    <li>Home</li>
    <li>About</li>
    <li>Contact</li>
</ul>
```

Result:

```text id="3p8k4z"
Home
About
Contact
```

Now you can build your own design.

---

# 11. Styling List Items

List items can be styled with normal CSS properties.

```css id="p9r6x1"
li {
    padding: 10px;
    margin-bottom: 5px;
    background-color: #f2f2f2;
}
```

Result:

```text id="9c7w2v"
┌────────────────────┐
│ HTML               │
└────────────────────┘
┌────────────────────┐
│ CSS                │
└────────────────────┘
┌────────────────────┐
│ JavaScript         │
└────────────────────┘
```

---

# 12. Styling Different List Items

CSS selectors can target individual list items.

For example:

```css id="w7n4v5"
li:first-child {
    font-weight: bold;
}
```

This selects the first `<li>`.

You can also use:

```css id="4o8x0m"
li:last-child {
    margin-bottom: 0;
}
```

And:

```css id="x9u1m3"
li:nth-child(even) {
    background-color: #f5f5f5;
}
```

This connects directly to the **pseudo-class selectors** you learned earlier.

---

# 13. Horizontal Lists

Lists are normally displayed vertically:

```text id="3z6l8h"
Home
About
Services
Contact
```

But CSS can turn them into horizontal navigation.

One simple approach is:

```css id="h2v0q7"
li {
    display: inline;
}
```

Result:

```text id="y8t1c4"
Home   About   Services   Contact
```

---

# 14. Horizontal Navigation with `inline-block`

Another approach is:

```css id="5t0k4s"
li {
    display: inline-block;
    margin-right: 20px;
}
```

This gives each item more control as a box.

Example:

```text id="4m7p9s"
┌──────┐  ┌──────┐  ┌──────────┐  ┌────────┐
│ Home │  │ About│  │ Services │  │ Contact│
└──────┘  └──────┘  └──────────┘  └────────┘
```

---

# 15. A Simple Navigation Menu

### HTML

```html id="6v9q2r"
<nav>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```

### CSS

```css id="b3p8x6"
nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

nav li {
    display: inline-block;
    margin-right: 20px;
}

nav a {
    text-decoration: none;
}
```

The list now behaves like a navigation menu.

---

# 16. Nested Lists

Lists can contain other lists.

```html id="5n7q3x"
<ul>
    <li>
        Frontend
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>JavaScript</li>
        </ul>
    </li>

    <li>
        Backend
        <ul>
            <li>Node.js</li>
            <li>Databases</li>
        </ul>
    </li>
</ul>
```

CSS can target different levels.

```css id="w3j5p2"
ul ul {
    list-style-type: circle;
}
```

The outer list might use:

```text id="4s0w8j"
● Frontend
    ○ HTML
    ○ CSS
    ○ JavaScript

● Backend
    ○ Node.js
    ○ Databases
```

---

# 17. Description Lists

Description lists use:

```html id="p6h4z8"
<dl>
    <dt>HTML</dt>
    <dd>Defines webpage structure.</dd>

    <dt>CSS</dt>
    <dd>Styles webpage content.</dd>
</dl>
```

The elements are:

```text id="0k3s7q"
<dl> → Description list
<dt> → Description term
<dd> → Description/details
```

They can be styled normally:

```css id="w1c7h9"
dt {
    font-weight: bold;
}

dd {
    margin-left: 20px;
}
```

---

# 18. Custom List Markers

Modern CSS also allows more customized markers.

The `::marker` pseudo-element can style the list marker.

Example:

```css id="2f7u9m"
li::marker {
    font-size: 20px;
}
```

You can also change the marker's color:

```css id="z5p1x4"
li::marker {
    color: red;
}
```

Example:

```text id="5u8m3q"
● HTML
● CSS
● JavaScript
```

The styling applies specifically to the marker.

---

# 19. `::marker` vs `list-style-type`

These have different purposes.

### `list-style-type`

Controls **what kind of marker** is used:

```css id="3h5b7k"
ul {
    list-style-type: square;
}
```

### `::marker`

Allows you to style the marker:

```css id="b9m2q6"
li::marker {
    font-size: 20px;
}
```

Think:

```text id="w8t5k2"
list-style-type
      ↓
"What marker?"


::marker
      ↓
"How should the marker look?"
```

---

# 20. Practical Example

### HTML

```html id="1y8k4s"
<ul class="skills">
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
    <li>React</li>
</ul>
```

### CSS

```css id="7n4m6p"
.skills {
    list-style: none;
    padding: 0;
    margin: 0;
}

.skills li {
    padding: 10px;
    margin-bottom: 5px;
    background-color: #f5f5f5;
}

.skills li::marker {
    color: blue;
}
```

Here:

```text id="c9x2v5"
.skills
   ↓
Removes default list styling

.skills li
   ↓
Styles each list item

li::marker
   ↓
Styles the marker
```

---

# 21. Important List Properties

| Property              | Purpose                                  |
| --------------------- | ---------------------------------------- |
| `list-style-type`     | Controls marker type                     |
| `list-style-position` | Controls marker position                 |
| `list-style-image`    | Uses an image as marker                  |
| `list-style`          | Shorthand for list-style properties      |
| `padding`             | Controls space inside the list/list item |
| `margin`              | Controls outside spacing                 |
| `display`             | Can change list layout                   |
| `::marker`            | Styles the list marker                   |

---

# 22. `list-style` Shorthand

Instead of:

```css id="o7f3m1"
ul {
    list-style-type: square;
    list-style-position: inside;
}
```

you can write:

```css id="p2k9s4"
ul {
    list-style: square inside;
}
```

For removing markers:

```css id="j5n8q2"
ul {
    list-style: none;
}
```

---

# 23. Lists and the Box Model

List elements are normal HTML elements, so the **CSS box model** applies to them.

For example:

```css id="x4m7p9"
li {
    padding: 10px;
    margin: 5px;
    border: 1px solid gray;
}
```

Each list item has:

```text id="v7k2m5"
        margin
    ┌───────────────┐
    │    border     │
    │  ┌─────────┐  │
    │  │ padding │  │
    │  │ content │  │
    │  └─────────┘  │
    └───────────────┘
```

So the box model concepts you've already learned apply directly to lists.

---

# 24. Mental Model

Think about list styling in layers:

```text id="f6q8m2"
             LIST
               │
       ┌───────┴────────┐
       │                │
     Marker           Items
       │                │
       │         ┌──────┴──────┐
       │         │             │
    Type/Style  Spacing      Content
       │         │             │
       ↓         ↓             ↓
 list-style   margin/padding   text
 ::marker     borders          links
```

---

# Quick Summary

* `<ul>` creates an **unordered list**.
* `<ol>` creates an **ordered list**.
* `<dl>` creates a **description list**.
* `<li>` represents a list item.
* `list-style-type` controls the marker type.
* `list-style-position` controls marker placement.
* `list-style-image` can use an image as a marker.
* `list-style` is the shorthand property.
* `list-style: none` removes default markers.
* `padding` and `margin` control list spacing.
* `display: inline` or `inline-block` can create horizontal lists.
* `:nth-child()`, `:first-child`, and `:last-child` can target specific list items.
* `::marker` can style the list marker itself.
* Lists can contain nested lists.
* Lists follow the normal CSS box model.

### One-line memory trick

```text id="m5v8q1"
list-style-type    → What marker?
list-style-position → Where is the marker?
list-style-image   → Which image?
::marker           → How does the marker look?
margin/padding     → How much space?
display             → How are items arranged?
```

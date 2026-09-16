# Data Attributes — `data-*`

Sometimes we need to store **custom information** on an HTML element. HTML provides a special mechanism for this. These are called **custom data attributes** or **data attributes**.

Basic syntax

```html
<div data-user-id="12345">Jane</div>
```

Here:

```text
data-user-id
     │
     └── Custom data attribute

12345
  │
  └── Stored value
```

The name must begin with:

```text
data-
```

For example:

```html
data-user-id data-product-id data-category data-theme data-status
```



## Why Do We Need Data Attributes?

Imagine building an online store.

We display several products:

```html
<div class="product" data-product-id="101">Laptop</div>

<div class="product" data-product-id="102">Keyboard</div>

<div class="product" data-product-id="103">Mouse</div>
```

Visually, the user sees:

```text
Laptop
Keyboard
Mouse
```

But the HTML also stores useful information:

```text
Laptop    → product ID: 101
Keyboard  → product ID: 102
Mouse     → product ID: 103
```

JavaScript can later read this information.



## Naming Data Attributes

Data attributes must start with **data**. Then they can have a descriptive name.

Examples:

```html
<div data-user-id="25"></div>

<button data-product-id="101">Add to Cart</button>

<div data-category="books"></div>

<div data-theme="dark"></div>
```

The `data-*` pattern is the standard mechanism for storing custom data on HTML elements.

---

## Reading Data Attributes with JavaScript

Suppose we have:

```html
<button data-product-id="101">Add to Cart</button>
```

JavaScript can access the value through `dataset`.

```javascript
const button = document.querySelector("button");

console.log(button.dataset.productId);
```

The `data-` portion becomes `dataset`, and the hyphenated name becomes camelCase.

```text
data-product-id
       │
       ▼
dataset.productId
```

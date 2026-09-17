# CSS Box Shadow

The `box-shadow` property adds a **shadow effect around an element's box**.

It is commonly used to create:

* Cards
* Buttons
* Panels
* Modals
* Floating elements
* Depth and elevation effects

---

# 1. Basic Box Shadow

### Syntax

```css
selector {
    box-shadow: offset-x offset-y blur-radius color;
}
```

### Example

```css
.card {
    box-shadow: 5px 5px 10px gray;
}
```

```text
                  Shadow
                    ↓
        ┌──────────────────┐
        │                  │
        │      CARD        │
        │                  │
        └──────────────────┘
             ↘
              ──────────────
```

The shadow appears around the element based on the values provided.

---

# 2. Understanding the Values

Consider:

```css
.card {
    box-shadow: 5px 5px 10px gray;
}
```

The values mean:

```text
5px     → offset-x
5px     → offset-y
10px    → blur-radius
gray    → color
```

Let's understand them individually.

---

## 2.1 Horizontal Offset — `offset-x`

The first value controls the **horizontal position** of the shadow.

```css
box-shadow: 10px 0 5px gray;
```

```text
Element
┌──────────────┐
│              │
│     CARD     │────────→ Shadow
│              │
└──────────────┘
```

### Positive value

Moves the shadow to the **right**.

```css
box-shadow: 10px 0 5px gray;
```

### Negative value

Moves the shadow to the **left**.

```css
box-shadow: -10px 0 5px gray;
```

---

# 3. Vertical Offset — `offset-y`

The second value controls the **vertical position** of the shadow.

```css
box-shadow: 0 10px 5px gray;
```

Positive values move the shadow **down**.

```text
┌──────────────┐
│     CARD     │
└──────────────┘
       ↓
    Shadow
```

Negative values move the shadow **up**.

```css
box-shadow: 0 -10px 5px gray;
```

---

# 4. Blur Radius

The third value controls how **soft or sharp** the shadow is.

```css
box-shadow: 5px 5px 0 black;
```

This creates a relatively sharp shadow.

```css
box-shadow: 5px 5px 20px black;
```

This creates a much softer shadow.

```text
Small blur:

████████████
████████████


Large blur:

░░░░▒▒████▒▒░░░
```

A larger blur value creates a more spread-out, softer-looking shadow.

---

# 5. Shadow Color

The last value controls the shadow's color.

```css
.card {
    box-shadow: 5px 5px 10px black;
}
```

You can use different CSS color formats:

```css
box-shadow: 5px 5px 10px red;
```

```css
box-shadow: 5px 5px 10px #888;
```

```css
box-shadow: 5px 5px 10px rgb(0, 0, 0);
```

For modern UI designs, a transparent black shadow is common:

```css
.card {
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}
```

The alpha value makes the shadow partially transparent.

---

# 6. The Complete Basic Syntax

The commonly used form is:

```css
box-shadow: offset-x offset-y blur-radius color;
```

For example:

```css
.card {
    box-shadow: 4px 6px 12px rgba(0, 0, 0, 0.2);
}
```

Think of it as:

```text
4px    → move right
6px    → move down
12px   → make it soft
0.2    → make it subtle
```

---

# 7. Spread Radius

There is another optional value called the **spread radius**.

The extended syntax is:

```css
box-shadow: offset-x offset-y blur-radius spread-radius color;
```

Example:

```css
.card {
    box-shadow: 5px 5px 10px 3px gray;
}
```

Here:

```text
5px  → horizontal offset
5px  → vertical offset
10px → blur
3px  → spread
gray → color
```

### What does spread do?

The spread radius controls how much the shadow **expands or contracts** before the blur is applied.

Positive spread:

```css
box-shadow: 0 0 10px 5px gray;
```

The shadow becomes larger.

Negative spread:

```css
box-shadow: 0 0 10px -3px gray;
```

The shadow becomes smaller.

---

# 8. No Offset Shadow

You don't always need to move the shadow.

```css
.card {
    box-shadow: 0 0 10px gray;
}
```

Here:

```text
offset-x = 0
offset-y = 0
blur     = 10px
```

The shadow surrounds the element.

This is useful for cards and panels.

---

# 9. `inset` Shadow

By default, the shadow appears **outside** the element.

You can use `inset` to place the shadow **inside** the element.

### Outside shadow

```css
.card {
    box-shadow: 0 4px 10px gray;
}
```

```text
      Shadow
         ↓
   ┌─────────────┐
   │    CARD     │
   └─────────────┘
```

### Inside shadow

```css
.card {
    box-shadow: inset 0 0 10px gray;
}
```

```text
┌─────────────────┐
│ ░░░░░░░░░░░░░░░ │
│ ░     CARD    ░ │
│ ░░░░░░░░░░░░░░░ │
└─────────────────┘
       ↑
   Inner shadow
```

`inset` changes the shadow from an **outer shadow** to an **inner shadow**.

---

# 10. Multiple Box Shadows

You can apply multiple shadows to the same element.

Separate each shadow with a comma.

```css
.card {
    box-shadow:
        0 4px 10px rgba(0, 0, 0, 0.2),
        0 8px 20px rgba(0, 0, 0, 0.1);
}
```

The browser layers the shadows together.

This can create more complex visual effects.

---

# 11. Box Shadow on Cards

One of the most common uses of `box-shadow` is a card.

```css
.card {
    width: 300px;
    padding: 20px;
    background-color: white;

    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
```

Conceptually:

```text
       ┌───────────────────┐
       │                   │
       │       CARD        │
       │                   │
       └───────────────────┘
        ░░░░░░░░░░░░░░░░░░
          Soft Shadow
```

The shadow makes the card appear slightly elevated from the page.

---

# 12. Box Shadow with Border Radius

`box-shadow` works naturally with rounded elements.

```css
.card {
    border-radius: 12px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}
```

The shadow follows the rounded shape of the element.

```text
       ╭─────────────────╮
      ╱                   ╲
     │        CARD         │
      ╲                   ╱
       ╰─────────────────╯
          ░░░░░░░░░░░
            Shadow
```

---

# 13. Box Shadow on Buttons

Shadows can also be used to give buttons a raised appearance.

```css
.button {
    padding: 10px 20px;
    border: none;
    border-radius: 8px;

    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
```

You can change the shadow when the button is pressed:

```css
.button {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.button:active {
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
```

This can create the visual impression that the button moves downward.

---

# 14. Box Shadow Does Not Take Up Layout Space

This is an important difference between `box-shadow` and the CSS box model.

A shadow is **visual** and does not increase the element's layout dimensions.

For example:

```css
.card {
    width: 300px;
    height: 200px;
    box-shadow: 0 10px 20px gray;
}
```

The element's declared dimensions are still:

```text
Width  = 300px
Height = 200px
```

The shadow does not add extra width or height to the layout.

Compare this with a border:

```text
Border
  ↓
Part of the box model

Box Shadow
  ↓
Visual effect outside the box
```

---

# 15. Border vs Outline vs Box Shadow

These three properties can look similar, but they have different purposes.

| Property     | Purpose                                     | Takes layout space? |
| ------------ | ------------------------------------------- | ------------------- |
| `border`     | Defines the element's boundary              | Yes*                |
| `outline`    | Draws an additional line outside the border | No                  |
| `box-shadow` | Creates a shadow/depth effect               | No                  |

* The effect of the border on declared dimensions depends on `box-sizing`.

```text
             OUTLINE
        ┌─────────────────┐
        │                 │
        │     BORDER      │
        │   ┌─────────┐   │
        │   │ CONTENT │   │
        │   └─────────┘   │
        │                 │
        └─────────────────┘
          ░░░░░░░░░░░░░░
            BOX SHADOW
```

---

# 16. Common Box Shadow Examples

### Subtle card

```css
.card {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
```

### Strong shadow

```css
.card {
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
}
```

### Shadow around all sides

```css
.card {
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
}
```

### Inner shadow

```css
.card {
    box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.2);
}
```

### Colored shadow

```css
.button {
    box-shadow: 0 5px 15px rgba(100, 50, 255, 0.3);
}
```

---

# Mental Model

Think of `box-shadow` as giving an element a **shadow cast around its box**.

```text
              Light
               ↓

        ┌───────────────┐
        │               │
        │     BOX       │
        │               │
        └───────────────┘
               ↓
          ░░░░░░░░░░
        ░░░░ SHADOW ░░░░
```

Remember the values:

```text
box-shadow:
    offset-x
    offset-y
    blur
    spread
    color
```

And the optional keyword:

```text
inset → shadow inside the element
```

---

# Quick Summary

```css
box-shadow: 5px 5px 10px gray;
```

| Part   | Meaning           |
| ------ | ----------------- |
| `5px`  | Horizontal offset |
| `5px`  | Vertical offset   |
| `10px` | Blur radius       |
| `gray` | Shadow color      |

With spread:

```css
box-shadow: 5px 5px 10px 3px gray;
```

With an inner shadow:

```css
box-shadow: inset 0 0 10px gray;
```

With multiple shadows:

```css
box-shadow:
    0 4px 10px rgba(0, 0, 0, 0.2),
    0 8px 20px rgba(0, 0, 0, 0.1);
```

### The key idea

> **`box-shadow` adds visual depth around an element without taking up layout space.**

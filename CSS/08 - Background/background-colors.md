# CSS Background — Colors

A website's background is one of the first things users notice. CSS provides several ways to define background colors, including **named colors, HEX, RGB, RGBA, HSL, and HSLA**.

---

## Background Color

The `background-color` property is used to set the background color of an element.

Syntax:

```css
selector {
  background-color: value;
}
```

Example:

```css
body {
  background-color: lightblue;
}
```

This gives the entire page a light blue background.

Another example:

```css
.card {
  background-color: periwinkle;
}
```

Only the elements with the `card` class will have a periwinkle background.

---

### Named Colors

CSS provides many predefined color names that can be used directly.

Example:

```css
background-color: red;
background-color: blue;
background-color: green;
background-color: yellow;
background-color: orange;
background-color: purple;
background-color: pink;
background-color: black;
background-color: white;
```

---

### HEX Colors

**HEX** stands for **hexadecimal**.

HEX colors are written using a `#` followed by six hexadecimal characters.

Syntax:

```css
#RRGGBB
```

Where:

- `RR` → Red
- `GG` → Green
- `BB` → Blue

Each pair can have a value from:

```text
00 → 00
...
FF → 255
```

Example:

```css
.box {
  background-color: #ff0000;
}
```

This represents red.

```text
#RRGGBB
 │ │ │
 │ │ └── Blue
 │ └──── Green
 └────── Red
```

#### Common HEX colors

```css
background-color: #ff0000; /* Red */
background-color: #00ff00; /* Green */
background-color: #0000ff; /* Blue */
background-color: #000000; /* Black */
background-color: #ffffff; /* White */
```

#### Short HEX notation

Some HEX colors can be shortened from six characters to three. This works when each pair contains the same character.

Example:

```
#ffffff becomes #fff
#ff0000 becomes #f00
```

---

### RGB Colors

**RGB** stands for **Red**, **Green**, and **Blue**. RGB represents a color by specifying the intensity of these three channels.

Syntax:

```css
rgb(red, green, blue)
```

Each value normally ranges from:

```text
0 → 255
```

Example:

```css
.box {
  background-color: rgb(255, 0, 0);
}
```

This creates red.

```text
rgb(255, 0, 0)
    │    │  │
    │    │  └── Blue = 0
    │    └───── Green = 0
    └────────── Red = 255
```

---

### RGBA Colors

**RGBA** extends RGB by adding an **alpha channel**. The alpha value controls **transparency**.

Syntax:

```css
rgba(red, green, blue, alpha)
```

The first three values are RGB values. The fourth value is:

```text
0 → completely transparent
1 → completely opaque
```

Example:

```css
.box {
  background-color: rgba(255, 0, 0, 0.5);
}
```

This creates red with **50% opacity**.

---

### HSL Colors

**HSL** stands for **Hue**, **Saturation**, and **Lightness**.

Syntax:

```css
hsl(hue, saturation, lightness)
```

#### Hue

Hue represents the basic color. It is represented using degrees from:

```text
0° → 360°
```

A simplified color wheel:

```text
              0° / 360°
                  Red
                   |
       300°       |       60°
      Magenta     |      Yellow
            \     |     /
             \    |    /
              \   |   /
               \  |  /
                \ | /
                 \|/
                 /|\
                / | \
               /  |  \
              /   |   \
             /    |    \
       240°       |      120°
        Blue      |      Green
                   |
                 180°
                  Cyan
```

#### Saturation

Saturation controls how intense or vivid the color is. It is represented as a percentage:

```text
0%   → no saturation
100%  → full saturation
```

#### Lightness

Lightness controls how light or dark the color is.

It is also represented as a percentage:

```text
0%   → black
50%  → normal color
100% → white
```

---

### HSLA Colors

**HSLA** adds an alpha channel to HSL. The first three values define the color, while the fourth controls transparency.

Syntax:

```css
hsla(hue, saturation, lightness, alpha)
```

Example:

```css
.box {
  background-color: hsla(0, 100%, 50%, 0.5);
}
```

This creates a semi-transparent red background.

---

## Comparing the Color Formats

The same color can often be represented using different formats. For example, red can be written as:

```css
/* Named color */
background-color: red;

/* HEX */
background-color: #ff0000;

/* RGB */
background-color: rgb(255, 0, 0);

/* RGBA */
background-color: rgba(255, 0, 0, 1);

/* HSL */
background-color: hsl(0, 100%, 50%);

/* HSLA */
background-color: hsla(0, 100%, 50%, 1);
```

They represent the same basic red color.

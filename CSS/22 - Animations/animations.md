# Animations

CSS can add **movement, visual changes, and interactive effects** to HTML elements. For example, we can make an element:

- Move
- Rotate
- Scale
- Change color
- Fade in or out
- Slide
- Grow or shrink
- Animate continuously
- Change between multiple visual states

---

## Transforms

The CSS `transform` property allows us to **visually transform an element**. It can:

- Move an element
- Rotate an element
- Resize an element
- Skew an element

Syntax:

```css
selector {
  transform: function(value);
}
```

### `translate()`

`translate()` moves an element from its original position.

```css
.box {
  transform: translate(50px, 20px);
}
```

This means:

```text
50px → horizontally
20px → vertically
```

```text
Original
┌───────┐
│ BOX   │
└───────┘
      ↘
       ┌───────┐
       │ BOX   │
       └───────┘
       New position
```

`transform` changes the **visual appearance/position** without changing the element's normal layout position.

### `translateX()` and `translateY()`

Moves an element horizontally. Positive values move it to the right. Negative values move it to the left.

Moves an element vertically. Positive values move it downward. Negative values move it upward.

### `translate3d()`

Transforms can also work in three dimensions.

```css
.box {
  transform: translate3d(20px, 30px, 40px);
}
```

The values represent:

```text
X → horizontal
Y → vertical
Z → depth
```

### `rotate()`

`rotate()` rotates an element. The value is usually given in degrees.

```css
transform: rotate(0deg);
transform: rotate(45deg);
transform: rotate(90deg);
transform: rotate(180deg);
```

### `scale()`

`scale()` changes the size of an element.

```css
/* Normal size */
transform: scale(1);
```

```css
/* 50% larger */
transform: scale(1.5);
```

```css
/* Half the size */
transform: scale(0.5);
```

### `scaleX()` and `scaleY()`

We can scale an element along a specific axis.

#### Horizontal

```css
.box {
  transform: scaleX(1.5);
}
```

#### Vertical

```css
.box {
  transform: scaleY(1.5);
}
```

### `skew()`

`skew()` tilts an element.

```css
.box {
  transform: skew(20deg, 10deg);
}
```

The first value controls the X-axis and the second controls the Y-axis.

We can also use:

```css
transform: skewX(20deg);
```

or:

```css
transform: skewY(20deg);
```

### Transform Origin

By default, transformations generally happen around the **center** of an element. The `transform-origin` property changes that point.

Common values:

```css
transform-origin: center;
transform-origin: top;
transform-origin: bottom;
transform-origin: left;
transform-origin: right;
transform-origin: top left;
```

We can also use percentages or lengths:

```css
transform-origin: 0 0;
```

---

## Transitions

A **transition** creates a smooth change between two CSS states. Without a transition the change happens immediately. With a transition the change happens smoothly over mentioned time in seconds.

### `transition-property`

Specifies which property should transition.

```css
button {
  transition-property: background-color;
}
```

We can transition multiple properties:

```css
button {
  transition-property: background-color, transform;
}
```

### `transition-duration`

Controls how long the transition takes.

```css
button {
  transition-duration: 0.3s;
}
```

### `transition-timing-function`

Controls the **speed pattern** of the transition.

Common values:

```css
transition-timing-function: linear; /* same speed */
transition-timing-function: ease; /* slow → fast → slow */
transition-timing-function: ease-in; /* slow → fast */
transition-timing-function: ease-out; /* fast → slow */
transition-timing-function: ease-in-out; /* slow → fast → slow */
```

### `transition-delay`

Controls how long the browser waits before starting the transition.

```css
button {
  transition-delay: 0.2s;
}
```

### Transition Shorthand

Instead of writing:

```css
button {
  transition-property: background-color;
  transition-duration: 0.3s;
  transition-timing-function: ease;
  transition-delay: 0s;
}
```

We can use:

```css
button {
  transition: background-color 0.3s ease;
}
```

---

## Keyframe Animations

CSS **keyframe animations** are used when we want an element to go through multiple stages of animation.

### Basic structure

```css
@keyframes animation-name {
  from {
    /* starting styles */
  }

  to {
    /* ending styles */
  }
}
```

Example:

```css
@keyframes moveBox {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(200px);
  }
}
```

Then apply it:

```css
.box {
  animation: moveBox 2s;
}
```

---

### `from` and `to`

The simplest keyframe animation has two stages:

```css
@keyframes fade {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
```

Then:

```css
.box {
  animation: fade 1s;
}
```

The element gradually changes from:

```text
opacity: 0
      ↓
opacity: 1
```

### Percentage Keyframes

Keyframes can contain multiple stages.

```css
@keyframes moveBox {
  0% {
    transform: translateX(0);
  }

  50% {
    transform: translateX(200px);
  }

  100% {
    transform: translateX(0);
  }
}
```

This means:

```text
0%      → starting position
50%     → move right
100%    → return to starting position
```

### Applying an Animation

Use the `animation` property. The basic shorthand is:

```text
animation: name duration;
```

### `animation-name`

Specifies the name of the `@keyframes` animation.

```css
.box {
  animation-name: moveBox;
}
```

### `animation-duration`

Controls how long one animation cycle takes.

```css
.box {
  animation-duration: 2s;
}
```

### `animation-timing-function`

Controls the speed pattern of the animation.

Common values:

```css
animation-timing-function: linear;
animation-timing-function: ease;
animation-timing-function: ease-in;
animation-timing-function: ease-out;
animation-timing-function: ease-in-out;
```

### `animation-delay`

Delays the beginning of the animation.

```css
.box {
  animation-delay: 1s;
}
```

The browser waits one second before starting the animation.

---

### `animation-iteration-count`

Controls how many times the animation runs.

```css
.box {
  animation-iteration-count: 3;
}
```

The animation runs three times.

We can also use:

```css
animation-iteration-count: infinite;
```

This makes the animation repeat continuously.

### `animation-direction`

Controls the direction in which the animation plays.

Common values:

```css
animation-direction: normal;
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;
```

### `animation-fill-mode`

Controls the styles applied before and/or after the animation.

Common values:

```css
animation-fill-mode: none;
animation-fill-mode: forwards;
animation-fill-mode: backwards;
animation-fill-mode: both;
```

### `animation-play-state`

Controls whether the animation is running or paused.

```css
.box {
  animation-play-state: running;
}
```

To pause:

```css
.box {
  animation-play-state: paused;
}
```

---

### Animation Shorthand

Instead of writing:

```css
.box {
  animation-name: moveBox;
  animation-duration: 2s;
  animation-timing-function: ease;
  animation-delay: 0s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```

we can use:

```css
.box {
  animation: moveBox 2s ease 0s infinite alternate;
}
```

The shorthand combines multiple animation properties.

---

## Transform vs Transition vs Animation

These three concepts are related but different.

| Concept      | Purpose                                                        |
| ------------ | -------------------------------------------------------------- |
| `transform`  | Changes an element's visual position, size, rotation, or shape |
| `transition` | Smoothly changes a property from one state to another          |
| `@keyframes` | Defines multiple stages of an animation                        |
| `animation`  | Applies a keyframe animation to an element                     |

---

## Accessibility and Reduced Motion

Some users prefer less motion because animations can cause discomfort or distraction. CSS provides the `prefers-reduced-motion` media feature.

Example:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms;
    animation-iteration-count: 1;
    transition-duration: 0.01ms;
    scroll-behavior: auto;
  }
}
```

The goal is to reduce unnecessary motion for users who have requested reduced motion at the operating-system/browser level.

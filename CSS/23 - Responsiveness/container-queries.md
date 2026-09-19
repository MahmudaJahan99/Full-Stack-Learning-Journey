# Container Queries

Container queries make decisions based on the **size of a containing element**. fThis is especially useful for reusable components.

Imagine the same card component is used in two places:

```text
┌───────────────────────────────┐
│ Main Content                  │
│                               │
│ ┌───────────────────────────┐ │
│ │         Card              │ │
│ └───────────────────────────┘ │
└───────────────────────────────┘

┌───────────────┐
│ Sidebar       │
│               │
│ ┌───────────┐ │
│ │   Card    │ │
│ └───────────┘ │
└───────────────┘
```

The viewport has not changed. But the card's available space is different. A media query sees the same viewport. But a container query allows the card to respond to **its own container**.

## Creating a Query Container

First, define an element as a query container:

```css
.card-container {
  container-type: inline-size;
}
```

Now the container can be used for container queries.

Example:

```css
.card-container {
  container-type: inline-size;
}

@container (min-width: 500px) {
  .card {
    display: flex;
  }
}
```

Meaning:

```text
Container width ≥ 500px
        ↓
Change .card layout
```

Notice that we are not checking the viewport width. We are checking the **container's width**.

## `container-type`

A common value is `container-type: inline-size;`. This allows queries based on the container's **inline dimension**, which generally corresponds to its width in a normal horizontal writing mode.

## Named Containers

A container can also have a name:

```css
.card-wrapper {
  container-type: inline-size;
  container-name: card;
}
```

Then:

```css
@container card (min-width: 500px) {
  .card {
    display: flex;
  }
}
```

This is useful when a component has multiple possible containers.

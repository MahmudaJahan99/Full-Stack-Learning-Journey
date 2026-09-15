# Lists and Types

Lists are used to **group related pieces of information** into a structured collection. Instead of writing related information as separate paragraphs we can tell the browser that these items belong to the same list.

HTML provides three main types of lists:

```text
                    HTML Lists
                        │
          ┌─────────────┼─────────────┐
          │             │             │
          ▼             ▼             ▼
      Ordered       Unordered     Definition
       List            List          List
       <ol>            <ul>          <dl>
          │
          │
          └──────────────┐
                         ▼
                    Nested Lists
```

---

## Quick Comparison

| List Type       | Element                             | Use When                           |
| --------------- | ----------------------------------- | ---------------------------------- |
| Ordered List    | `<ol>`                              | Sequence/order matters             |
| Unordered List  | `<ul>`                              | Order doesn't matter               |
| Definition List | `<dl>`                              | Terms have associated descriptions |
| Nested List     | `<ul>` / `<ol>` inside another list | Information has multiple levels    |

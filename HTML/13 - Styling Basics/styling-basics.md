# Styling Basics

CSS (**Cascading Style Sheets**) is used to control the **presentation and appearance** of HTML documents.

HTML gives a webpage its structure. CSS controls how that structure looks.

```text
HTML
 │
 └── Structure + Meaning
          │
          ▼
        CSS
          │
          └── Appearance + Presentation
```

There are three common ways to apply CSS to HTML.

```text
                    CSS
                     │
          ┌──────────┼──────────┐
          │          │          │
          ▼          ▼          ▼
       Inline     Internal    External
          │          │          │
     style=""     <style>    .css file
```

---

## Comparing the Three Methods

| Feature                      | Inline       | Internal         | External      |
| ---------------------------- | ------------ | ---------------- | ------------- |
| Where?                       | `style=""`   | `<style>`        | `.css` file   |
| CSS location                 | HTML element | HTML document    | Separate file |
| Reusable?                    | Low          | Within that page | High          |
| HTML cleanliness             | Low          | Medium           | High          |
| Good for large websites?     | ❌           | Usually not      | ✅            |
| Can style multiple elements? | Limited      | Yes              | Yes           |
| Can style multiple pages?    | ❌           | ❌ directly      | ✅            |
| Easy to maintain?            | ❌           | Medium           | ✅            |

---

## When Should We Use Each One?

### Inline CSS

- One-off styles
- Very specific situations
- Certain dynamically generated styles

### Internal CSS

- Small single-page experiments
- Learning CSS
- A page with unique styles
- Quick prototypes

### External CSS

- Multi-page websites
- Larger projects
- Reusable styles
- Consistent design systems
- Production websites

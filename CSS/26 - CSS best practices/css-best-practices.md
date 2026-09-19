# CSS Best Practices

Writing CSS is not only about making a website look good. Good CSS should also be:

- **Maintainable**
- **Performant**
- **Accessible**
- **Responsive**
- **Consistent**
- **Easy to understand**

Two important areas of CSS best practices are **performance** and **accessibility**

---

## Performance

CSS affects how quickly a browser can **parse, calculate, and render** a webpage. Poorly structured or unnecessarily complex CSS can make a website harder for the browser to process and harder for developers to maintain.

The goal is not to make every CSS rule extremely short. The goal is to write **clear CSS that does only what is necessary**.

1. **Avoid Unnecessary CSS** - Avoiding unnecessary rules keeps the stylesheet cleaner.
2. **Avoid Excessively Complex Selectors** - A simpler class can be easier to maintain
3. **Keep Selectors Simple** - Prefer meaningful classes over deeply nested selectors. Simple selectors are easier to understand and modify.
4. **Avoid Excessive `!important`** - Although it can sometimes be useful, relying heavily on it can make CSS difficult to manage.
5. **Reuse Styles** - If multiple elements share the same styling, create a reusable class.
6. **Use CSS Variables for Repeated Values** - CSS variables are useful for maintaining consistency. If a value changes, we can update it in one place.
7. **Avoid Overly Large CSS Files** - Keep CSS organized so that developers can find and understand styles easily.
8. **Remove Unused CSS** - Unused CSS can: increase stylesheet size, make the project harder to maintain, and make debugging more confusing.
9. **Optimize Large Assets** - Use appropriately sized and optimized assets.
10. **Be Careful with Background Images** - Large background images can be expensive, especially for large hero sections.
11. **Prefer Efficient Animation Properties** - The exact performance impact depends on the situation and browser rendering pipeline, but avoiding unnecessary layout changes is a useful general practice.
12. **Respect Reduced Motion Preferences** - Some users prefer reduced motion because animations can be distracting or uncomfortable.

---

## Accessibility

> **Accessibility** means designing websites that can be used by as many people as possible, including people with disabilities. Accessibility can involve:

- vision
- hearing
- motor abilities
- cognition
- assistive technology

CSS plays an important role in visual accessibility. However, accessibility is **not only a CSS concern**. HTML structure, semantics, keyboard interaction, JavaScript behavior, and content also matter.

1. **Maintain Good Color Contrast** - Text should have enough contrast against its background so that it is easier to read.
2. **Don't Rely Only on Color** - Color should not be the only way to communicate important information.
3. **Visible Focus States** - A visible focus indicator helps users navigate interactive elements using the keyboard.
4. **Don't Remove Focus Indicators Without Replacement**
5. **Use `:focus-visible`** - `:focus-visible` can be useful when you want to provide a visible focus indicator when the browser determines that it is relevant, such as during keyboard navigation.
6. **Don't Use Tiny Text** - Use a comfortable base size and responsive typography when needed:
7. **Use Relative Units When Appropriate** - Relative units can make interfaces more flexible.
8. **Don't Hide Important Content with CSS** - There are situations where content needs to be visually hidden while remaining available to screen readers.
9. **Be Careful with `opacity: 0`** - This makes an element invisible, but it does not necessarily remove the element from interaction or accessibility. Invisible does not always mean removed.
10. **Don't Disable Pointer/Keyboard Interaction Accidentally** - Be careful when using properties that change interaction behavior. A visually attractive interface is not useful if users cannot operate it.
11. **Respect Text Zoom and User Settings** - Avoid designing layouts that depend on one exact font size or viewport size. Prefer layouts that can accommodate changing text sizes.
12. **Use `overflow` Carefully** - If the content becomes larger, important information may be cut off. Whenever possible, allow content to grow naturally.
13. **Don't Use CSS to Replace Semantic HTML** - CSS should not be used to make an element visually behave like something it is not. Accessibility starts with **correct HTML semantics**, not just CSS.

# CSS Responsiveness

Responsive web design means creating websites that **adapt to different screen sizes, devices, and available space**. Instead of creating a completely different website for every device, CSS allows us to create layouts that **respond to the available space**. A website should work well on:

- 📱 Mobile phones
- 📱 Tablets
- 💻 Laptops
- 🖥️ Desktop monitors
- Large and small screens

A responsive website changes its layout, sizing, spacing, and typography depending on the screen or container available to it. The same website can rearrange itself depending on the available space.

```text
        Desktop
┌───────────────────────────────┐
│  Header                       │
├─────────────┬─────────────────┤
│   Sidebar   │     Content     │
│             │                 │
└─────────────┴─────────────────┘


        Mobile
┌─────────────────┐
│     Header      │
├─────────────────┤
│     Content     │
│                 │
│                 │
└─────────────────┘
```

---

# Media Queries vs Container Queries vs Responsive Typography

| Technique             | Responds To             | Main Purpose                   |
| --------------------- | ----------------------- | ------------------------------ |
| Media Queries         | Viewport/device         | Page-level responsiveness      |
| Container Queries     | Container size          | Component-level responsiveness |
| Responsive Typography | Available size/viewport | Flexible, readable text        |

---
name: page-section-builder
description: Guide for creating consistent, well-structured page sections. Use this when asked to add a new section or page component.
---

# Page Section Builder

When creating a new page section, follow these steps:

## Structure
1. Use a <section> element with a descriptive id
2. Include an <h2> heading as the first child
3. Wrap content in a container div with class "section-content"
4. Add a scroll-in animation

## Styling rules
- Max width: 800px, centered
- Padding: 4rem 2rem
- Alternate background colors between sections (white / light gray)
- Color palette: #2563eb (primary), #1e293b (text), #f8fafc (light bg)

## Animation
Add this CSS for scroll-in:

.section-content {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp 0.6s ease forwards;
}

@keyframes fadeInUp {
  to { opacity: 1; transform: translateY(0); }
}
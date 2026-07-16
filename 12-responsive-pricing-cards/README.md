# Responsive Pricing Cards

## Feature Overview
Modern pricing pages need to look great across all devices and context areas. This module demonstrates how to build highly adaptive pricing cards using **Container Queries** for layout adjustments based on available space, and **`clamp()`** for fluid typography and spacing.

## Problem Statement
Traditional responsive design relies on viewport-based media queries (`@media`). However, when placing components like pricing cards into different contexts (e.g., a main page vs. a sidebar), they might break because the viewport is large, but their specific container is small. Furthermore, maintaining readable typography across all screen sizes often requires writing numerous media queries for font sizes and padding.

## Syntax Explanation

### Container Queries
Container Queries allow elements to adjust their styling based on the size of their containing element rather than the viewport.

```css
.pricing-grid {
  /* Establish a container for querying */
  container-type: inline-size;
  container-name: pricing;
}

.pricing-card {
  display: flex;
  flex-direction: row;
}

/* When the container is smaller than 600px, stack the card vertically */
@container pricing (max-width: 600px) {
  .pricing-card {
    flex-direction: column;
  }
}
```

### `clamp()` for Fluid Sizing
The `clamp()` function enables fluid values that scale dynamically between a minimum and maximum bound.

```css
.price-heading {
  /* min-size, preferred-size (scales with viewport/container), max-size */
  font-size: clamp(1.5rem, 5vw, 3rem);
  padding: clamp(1rem, 2vw + 1rem, 2.5rem);
}
```

## Browser Support
- **Container Queries:** Supported in all modern browsers (Chrome 105+, Safari 16+, Firefox 110+).
- **`clamp()`:** Broadly supported in all modern browsers.

## Practical Use Cases
- **Modular Components:** Creating UI components (like cards or widgets) that can be dropped into any layout and will adapt perfectly to their available space.
- **Fluid Typography:** Building dynamic headings that scale smoothly on mobile devices without requiring rigid media query breakpoints.
- **Dashboard Widgets:** Adjusting the layout or detail level of widgets depending on how many columns they occupy in a dashboard grid.

## Best Practices
- Define containers on parent layout wrappers rather than on every single element to optimize performance.
- Use `clamp()` for base text sizing, headings, and padding to create a seamless, fluid experience across varying screen dimensions.
- Combine Container Queries with CSS Grid/Flexbox to handle the macro-layout, using the queries for micro-layout adjustments inside the components.

## Key Takeaway
Container Queries and `clamp()` shift the focus of responsive design from the viewport to the component itself, enabling true modularity and perfectly fluid layouts.

## Official Documentation
- [MDN: CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)
- [MDN: clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)

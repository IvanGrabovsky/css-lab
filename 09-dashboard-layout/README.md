# Dashboard Layout

## Feature Overview
Modern dashboards require complex, highly responsive layouts that adapt not just to the viewport, but to the space available within specific containers. This module demonstrates how to build a robust dashboard layout using CSS Grid, **Subgrid**, and **Container Queries**.

## Problem Statement
Building flexible dashboard interfaces typically relies on complex media query breakpoints that are tied to the viewport. When components are reused in different areas (e.g., a sidebar vs. a main content area), viewport-based media queries fail to adapt the component properly to its parent's width. Furthermore, aligning nested elements (like product titles and prices) across sibling cards often requires fixed heights or JavaScript calculations.

## Syntax Explanation

### Container Queries
Allows styling an element based on the size of its parent container rather than the viewport.

```css
.container {
  container-type: inline-size;
}

@container (min-width: 600px) {
  .component {
    /* Styles applied when the container is wider than 600px */
  }
}
```

### Subgrid
Allows nested grids to participate in the sizing of their parent grid.

```css
.parent-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

.child-item {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}
```

## Browser Support
- **Container Queries:** Supported in all modern browsers (Chrome 105+, Safari 16+, Firefox 110+).
- **Subgrid:** Supported in all modern browsers (Chrome 117+, Safari 16+, Firefox 71+).

## Practical Use Cases
- **Widgets and Dashboard Cards:** Adjusting a widget's internal layout based on where it's placed in the dashboard grid.
- **Card Grids:** Aligning card headers, body content, and footers consistently across multiple cards using `subgrid`.
- **Responsive Layouts:** Shifting a main layout from a single column to a multi-column sidebar layout based on the available space.

## Best Practices
- Define `container-type: inline-size` on logical wrapper elements rather than globally.
- Use `subgrid` for aligning deeply nested content (like form labels or card sections) with the parent grid tracks.
- Combine Container Queries with CSS Grid to create truly modular, drop-in components.

## Key Takeaway
Container Queries shift the paradigm from responsive *pages* to responsive *components*. Combined with Subgrid, you can build highly robust, self-contained UI components that align perfectly and adapt to any context without viewport media queries.

## Official Documentation
- [MDN: CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)
- [MDN: Subgrid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Subgrid)

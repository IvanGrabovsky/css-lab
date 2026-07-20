# Dashboard Widgets

## Feature Overview
This module demonstrates how to build adaptable and engaging dashboard widgets using **Container Queries** for layout adjustments based on available space, and **Scroll-driven Animations** to animate data visualizations as they enter the viewport.

## Problem Statement
Widgets in a dashboard often need to be placed in various contexts (e.g., full width, half width, or constrained in a sidebar). Media queries based on viewport size are insufficient because a widget might be small even on a large screen if it is in a narrow column. Furthermore, animating data (like progress bars or charts) typically requires JavaScript intersection observers to trigger animations when the widget becomes visible.

## Syntax Explanation

### Container Queries
By defining a widget as a container, its internal elements can restructure themselves based on the widget's actual width.

```css
.widget {
  /* Establish the container */
  container-type: inline-size;
  container-name: widget;
}

/* Restructure the layout only when the widget itself is wide enough */
@container widget (min-width: 500px) {
  .widget-content {
    display: flex;
    justify-content: space-between;
  }
}
```

### Scroll-driven Animations
Using the `animation-timeline: view()` property, animations can be directly linked to an element's scroll position relative to the viewport.

```css
.progress-fill {
  /* Define the animation as normal */
  animation: fillProgress linear both;
  
  /* Link the animation progress to the element crossing the viewport */
  animation-timeline: view();
  
  /* Start when the element enters 10% from bottom, finish at 40% */
  animation-range: entry 10% cover 40%;
}

@keyframes fillProgress {
  to { width: var(--target-width); }
}
```

## Browser Support
- **Container Queries:** Supported in all modern browsers (Chrome 105+, Safari 16+, Firefox 110+).
- **Scroll-driven Animations:** Supported in Chrome 115+, Edge 115+. Partial/upcoming support in Firefox and Safari.

## Practical Use Cases
- **Modular Dashboard Systems:** Creating widgets that developers or users can place anywhere in a grid, trusting that the internal layout will adapt perfectly.
- **Data Visualizations:** Animating charts, graphs, and progress bars directly via CSS without relying on heavy JavaScript intersection observer libraries.
- **Scroll Effects:** Revealing cards or sections dynamically as a user scrolls down a long analytics page.

## Best Practices
- Name your containers (e.g., `container-name: widget`) to avoid unintended styling clashes when containers are nested.
- Keep scroll animations subtle. Use `animation-range` effectively so the animation completes while the element is still comfortably in the user's focus area.
- Provide a fallback state for browsers that do not support scroll animations (the `both` fill mode and `to` keyframes usually ensure the final state is applied gracefully).

## Key Takeaway
By combining Container Queries for structural flexibility with Scroll-driven Animations for interactive engagement, you can build powerful, JS-free widgets that elevate the user experience of any dashboard.

## Official Documentation
- [MDN: CSS Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)
- [MDN: animation-timeline](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timeline)

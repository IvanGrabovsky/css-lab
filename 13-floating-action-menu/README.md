# Floating Action Menu

## Feature Overview
This module demonstrates how to build a highly interactive Floating Action Button (FAB) that expands into a menu using **Anchor Positioning** to tether the menu to the button, and the **`:has()`** selector to handle the open/close state without any JavaScript.

## Problem Statement
Positioning a floating menu relative to a moving or dynamically placed button usually involves complex JavaScript calculations (like `getBoundingClientRect()`) or wrapping the elements in tightly coupled `position: relative` containers that can cause `z-index` or overflow clipping issues. Additionally, managing the state (open/closed) typically requires JS event listeners.

## Syntax Explanation

### `:has()` for State Management
Using a hidden checkbox (`.fab-checkbox`), we can toggle the state. The `:has()` selector on the container detects this state and styles the button and menu accordingly.

```css
/* Show the menu when the checkbox inside the container is checked */
.fab-container:has(.fab-checkbox:checked) .fab-menu {
  opacity: 1;
  visibility: visible;
  transform: translateY(0) scale(1);
}
```

### Anchor Positioning
We declare the main button as an anchor, and tell the menu to position itself relative to it, even if they aren't strictly parent/child in a relative positioning context.

```css
.fab-button {
  anchor-name: --main-fab;
}

.fab-menu {
  position: absolute;
  position-anchor: --main-fab;
  
  /* Position the bottom of the menu at the top of the FAB */
  bottom: anchor(top);
  
  /* Center it horizontally relative to the FAB's center */
  left: anchor(center);
  translate: -50% 0;
}
```

## Browser Support
- **`:has()`:** Supported in all modern browsers (Chrome 105+, Safari 15.4+, Firefox 121+).
- **Anchor Positioning:** Supported in Chrome 125+, Edge 125+, and currently limited support in Safari/Firefox.

## Practical Use Cases
- **Context Menus:** Showing popovers, tooltips, and action menus exactly where they are needed without worrying about overflow from parent containers.
- **Complex Navigations:** Building mega-menus or floating toolbars that stay attached to their trigger elements even during layout shifts.

## Best Practices
- Use semantic `<button>` elements for the actions, and a visually hidden checkbox combined with `<label>` for the CSS-only state toggle.
- Avoid using Anchor Positioning where simple Flexbox or Grid would suffice. Reserve it for out-of-flow elements (like popovers, tooltips, and floating menus).
- Ensure accessible names for the FAB and its items (e.g., using `aria-label`).

## Key Takeaway
By combining Anchor Positioning for layout decoupling and `:has()` for JS-free state management, you can build robust floating interfaces that are resilient to layout changes and free of JavaScript overhead.

## Official Documentation
- [MDN: CSS Anchor Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_anchor_positioning)
- [MDN: :has()](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)

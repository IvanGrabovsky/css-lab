# Interactive Form

## Feature Overview
Modern forms require immediate, contextual feedback to provide a good user experience. This module demonstrates how to build a highly interactive form component using **`:has()`** for state-driven styling and **Anchor Positioning** for contextual validation tooltips, all without JavaScript.

## Problem Statement
Providing real-time validation feedback in forms traditionally requires JavaScript to track input states (focus, blur, valid, invalid) and position tooltips or error messages relative to the input fields. This often leads to complex event listeners, state management, and manual DOM calculations for positioning floating elements.

## Syntax Explanation

### `:has()` for State Detection
The `:has()` pseudo-class allows a parent element to apply styles based on the state of its descendants.

```css
/* Style the wrapper when the input inside is invalid and not focused */
.form-group:has(input:invalid:not(:focus)) {
  --border-color: red;
}
```

### Anchor Positioning
Allows absolute positioning of an element relative to another specific element (the anchor).

```css
.input {
  anchor-name: --my-input;
}

.tooltip {
  position: absolute;
  position-anchor: --my-input;
  top: anchor(bottom);
  left: anchor(start);
}
```

## Browser Support
- **`:has()`:** Supported in all modern browsers (Chrome 105+, Safari 15.4+, Firefox 121+).
- **Anchor Positioning:** Supported in Chrome 125+, Edge 125+, currently limited support in Firefox and Safari.

## Practical Use Cases
- **Validation Tooltips:** Showing error messages positioned precisely next to invalid inputs.
- **Dynamic Form Layouts:** Changing the layout or highlighting sections of a form when specific fields are focused or filled.
- **Conditional Visibility:** Revealing additional form fields based on the state of previous inputs (e.g., checking a checkbox).

## Best Practices
- Combine `:has()` with native HTML validation attributes (`required`, `type="email"`, `pattern`) for robust CSS-only validation.
- Use Anchor Positioning for contextual help text or error messages to ensure they are always attached to the relevant input, regardless of layout changes.
- Ensure tooltips remain accessible by linking them to inputs using `aria-describedby` or similar attributes in production code.

## Key Takeaway
By combining the state-detecting power of `:has()` with the precise placement capabilities of Anchor Positioning, you can create rich, interactive, and responsive form experiences entirely in CSS.

## Official Documentation
- [MDN: :has() pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/:has)
- [MDN: CSS Anchor Positioning](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_anchor_positioning)

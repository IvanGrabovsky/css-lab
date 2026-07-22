# 16 — Command Palette

A modern command palette UI utilizing View Transitions for smooth state changes and `<dialog>` element.

## 🎯 What problem does this solve?

Creating command palettes, search modals, and complex overlay dialogs has traditionally required complex JavaScript for state management, focus trapping, and animations. By using the native `<dialog>` element combined with the View Transitions API, we can achieve smooth entering/exiting animations and excellent accessibility with minimal effort.

## ✨ Key Features Demonstrated

- **`<dialog>` Element**: Native focus trapping, backdrop support, and accessible modal behavior.
- **View Transitions API**: Smoothly animating the dialog in and out without complex CSS keyframe choreographies.
- **Modern Layout**: Using Grid and Flexbox to structure the palette contents.

## 💡 How it works

1. **Native Dialog**: The `<dialog>` element handles the heavy lifting of displaying the modal and dimming the background via the `::backdrop` pseudo-element.
2. **View Transitions**: When opening or closing the dialog, `document.startViewTransition()` is called (if supported) to automatically animate the state change, providing a native-feeling UI transition.
3. **Fallback Animation**: For browsers that don't yet support View Transitions, a standard CSS `@keyframes` animation provides a graceful fallback.

## 📝 Best Practices

- Always use the native `<dialog>` element for modals and command palettes unless building for extremely legacy browsers.
- Wrap UI state changes in `document.startViewTransition()` to progressively enhance the experience.
- Provide a CSS animation fallback for unsupported browsers.
- Ensure proper keyboard navigation (tabbing, arrow keys, Escape to close).

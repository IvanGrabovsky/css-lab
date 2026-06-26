# View Transitions

## 🧠 What is it?

View Transitions is a modern web API that enables smooth visual transitions between different UI states or pages.

It automatically animates changes in the DOM, creating seamless navigation and interface updates.

---

## 🧩 Basic Syntax

```css
::view-transition-old(root) {
  animation: fade-out 0.3s ease;
}

::view-transition-new(root) {
  animation: fade-in 0.3s ease;
}
```

---

## 💡 Example

A page smoothly fades between two states instead of changing instantly.

---

## 📖 Explanation

Normally, when the DOM changes, the browser immediately replaces the old content with the new one.

View Transitions capture the old and new states, then animate between them automatically.

---

## 🚀 Use Cases

- Single Page Applications (SPA)
- Multi-page websites
- Theme switching
- Gallery navigation
- Card expansion animations

---

## 📚 Official Documentation

MDN:
https://developer.mozilla.org/en-US/docs/Web/API/View_Transitions_API

---

## 🎯 Key Takeaway

View Transitions make UI changes feel smooth by animating between the old and new interface states.

# Container Queries

## 🧠 What is it?

Container Queries allow components to respond to the size of their container, not the viewport.

This makes truly reusable and responsive UI components possible.

## 🧩 Syntax

css

.card-wrapper {
container-type: inline-size;
}

@container (min-width: 500px) {
.card {
display: flex;
}
}

## 💡 Example

A card changes layout when its parent container becomes wider than 500px.

## 📖 Explanation

Traditional media queries depend on the browser width.

Container queries depend on the component's available space, making components portable and predictable.

## 🚀 Use Cases

Reusable card components

Dashboard widgets

Sidebar layouts

Design systems

## 📚 Official Documentation

MDN: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_container_queries

## 🎯 Key Takeaway

Media queries respond to the viewport.

Container queries respond to the component's container.

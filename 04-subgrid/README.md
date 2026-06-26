# Subgrid

## 🧠 What is it?

Subgrid is a CSS Grid feature that allows a nested grid to inherit the track sizing of its parent grid.

It helps maintain consistent alignment across complex layouts.

---

## 🧩 Syntax

```css
.child {
  display: grid;
  grid-template-columns: subgrid;
}
```

---

## 💡 Example

A card layout inherits the columns defined by its parent grid.

---

## 📖 Explanation

Normally nested grids create their own independent columns and rows.

Subgrid allows child elements to reuse the parent grid tracks, creating perfectly aligned layouts.

---

## 🚀 Use Cases

- Card grids
- Dashboards
- Pricing tables
- Editorial layouts
- Design systems

---

## 📚 Official Documentation

MDN:
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Subgrid

---

## 🎯 Key Takeaway

Subgrid lets nested layouts share the same grid structure as their parent.

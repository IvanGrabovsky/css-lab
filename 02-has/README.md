# :has()

## 🧠 What is it?

`:has()` is a relational CSS pseudo-class that allows you to style an element based on its descendants, siblings, or contained state.

It is often called the "parent selector" because it enables styling a parent when a child matches a condition.

---

## 🧩 Syntax

```css
selector:has(condition) {
  /* styles */
}
```

---

## 💡 Example

```css
.card:has(img) {
  border: 2px solid green;
}
```

Any `.card` containing an image will receive the border.

---

## 📖 Explanation

Normally CSS selects elements from parent → child.

`:has()` allows CSS to look inside an element and apply styles based on what it contains.

This makes many JavaScript-based UI interactions possible with pure CSS.

---

## 🚀 Use Cases

### Form Validation

```css
.form-group:has(input:invalid) {
  border-color: red;
}
```

### Highlight Selected Card

```css
.card:has(input:checked) {
  background: lightgreen;
}
```

### Navigation Menus

```css
li:has(ul) {
  font-weight: bold;
}
```

---

## 📚 Official Documentation

- MDN:
  https://developer.mozilla.org/en-US/docs/Web/CSS/:has

---

## 🎯 Key Takeaway

`:has()` allows CSS to react to content and state inside an element, making complex UI interactions possible without JavaScript.
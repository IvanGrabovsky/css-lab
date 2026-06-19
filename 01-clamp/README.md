# clamp()

## 🧠 What is it?

`clamp()` is a modern CSS function that allows you to create responsive values with a defined minimum, preferred, and maximum size.

It is widely used for fluid typography and responsive UI without media queries.

---

## 🧩 Syntax

clamp(min, preferred, max);

### Example

font-size: clamp(16px, 2vw, 32px);

## Explanation

-   **16px** → minimum size (never smaller than this)
-   **2vw** → preferred fluid value based on viewport width
-   **32px** → maximum size (never larger than this)

## Use cases

-   Fluid typography
-   Responsive spacing (margin, padding)
-   Button sizing
-   Border radius scaling
-   Layout responsiveness

## Official documentation

-   [MDN Web Docs – clamp()](https://developer.mozilla.org/en-US/docs/Web/CSS/clamp)
-   [CSS-Tricks guide – clamp()](https://css-tricks.com/almanac/functions/c/clamp/)

## Key takeaway

`clamp()` lets you build responsive designs that automatically adapt between a minimum and maximum value without media queries.

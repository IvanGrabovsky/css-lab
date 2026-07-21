# 15. Animated Gallery

This module demonstrates a highly interactive accordion-style image gallery built entirely with CSS. No JavaScript is required for the expansion animations or the peer-dimming effects.

## Techniques Demonstrated

1. **Flexbox Expansion**
   - The gallery is a Flex container where each `.gallery-panel` has `flex: 1`.
   - On `:hover`, the targeted panel receives `flex: 4`. The browser smoothly interpolates between these `flex` values, creating a satisfying accordion expansion effect.

2. **`:has()` Peer Dimming**
   - We use the powerful `:has()` pseudo-class to style sibling elements based on hover state.
   - `gallery:has(.gallery-panel:hover) .gallery-panel:not(:hover)`
   - Translation: *If the gallery has any panel currently being hovered, find all the panels that are NOT being hovered, and apply styles to them.*
   - This allows us to drop the `opacity` and apply a `grayscale()` filter to all un-hovered images, drawing focus entirely to the active image.

3. **Transition Choreography**
   - The `.panel-content` (text) remains hidden (`opacity: 0`) and translated down until the parent is hovered.
   - We apply a `transition-delay` to the text appearing so it waits until the panel has partially expanded before showing, preventing awkward text wrapping.

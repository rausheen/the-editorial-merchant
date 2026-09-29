# Design System Specification: The Editorial Merchant

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Digital Curator."** 

Moving away from the cluttered, "big-box" retail aesthetic, this system treats e-commerce as a high-end editorial experience. We achieve "Trustworthy" not through rigid grids and heavy borders, but through authoritative typography, vast expanses of white space (the "Ample" requirement), and a sophisticated layering of surfaces. 

The design breaks the "template" look by using intentional asymmetry—such as off-center hero text and overlapping product imagery—that guides the eye through a narrative rather than a list. We prioritize the "breath" between elements, ensuring that every product feels like a featured piece in a gallery.

---

## 2. Colors & Surface Architecture
The palette is anchored by a deep, intellectual Teal (`primary: #004253`) and supported by an expansive range of soft, warm neutrals.

### The "No-Line" Rule
To maintain a premium feel, **1px solid borders are strictly prohibited for sectioning.** Contrast and containment must be achieved through background shifts. For example, a product description section in `surface-container-low` (#f3f4f5) should sit directly against a `surface` (#f8f9fa) page background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. 
- **Base Level:** `surface` (#f8f9fa) for the main page canvas.
- **Secondary Level:** `surface-container-low` (#f3f4f5) for large layout blocks (e.g., a "Recommended" section).
- **Elevated Level:** `surface-container-lowest` (#ffffff) for interactive cards or floating menus.
This "nested" depth creates a natural, tactile hierarchy that feels integrated, not "pasted on."

### The "Glass & Gradient" Rule
For floating navigation or high-end modals, use a "Frosted Glass" effect. Utilize `surface` colors at 80% opacity with a `backdrop-blur` of 20px. 
**Signature Textures:** For primary CTAs, do not use a flat color. Apply a subtle linear gradient from `primary` (#004253) to `primary_container` (#005b71) at a 135-degree angle. This adds "soul" and depth to the action point.

---

## 3. Typography: Editorial Authority
We utilize a dual-typeface system to balance modern flair with high-utility readability.

*   **Display & Headlines (Plus Jakarta Sans):** This is our "Editorial Voice." Large scales (`display-lg` at 3.5rem) should be used with tight letter-spacing (-0.02em) to create a bold, confident brand presence.
*   **Body & Labels (Inter):** This is our "Functional Voice." Inter provides maximum legibility for product specs and long-form descriptions. Use `body-lg` (1rem) for standard descriptions to maintain the "premium" feel of larger text.

The hierarchy is designed to create a "Visual Path": The user's eye should hit the `display-md` headline, glide through the `title-md` sub-header, and settle on the `body-md` description.

---

## 4. Elevation & Depth
Depth is conveyed through **Tonal Layering** rather than structural lines.

*   **The Layering Principle:** Avoid shadows for static content. Use the difference between `surface-container-low` and `surface-container-highest` to define areas.
*   **Ambient Shadows:** For "Floating" elements (Product Cards on hover, Modals), use extra-diffused shadows.
    *   *Spec:* `0 20px 40px rgba(25, 28, 29, 0.06)` (using a tinted version of `on-surface`).
*   **The "Ghost Border" Fallback:** If a border is required for accessibility (e.g., input fields), use `outline-variant` (#bfc8cc) at **20% opacity**. Never use 100% opaque borders.
*   **Glassmorphism:** Use semi-transparent `surface_container_lowest` (#ffffff at 0.7 alpha) for floating headers to allow product imagery to bleed through softly as the user scrolls.

---

## 5. Components

### Buttons
*   **Primary:** Rounded `full` (9999px) or `md` (0.75rem). Gradient fill (Primary to Primary Container). Label: `title-sm` (Inter), white.
*   **Secondary:** Ghost style. No background. `Ghost Border` (outline-variant @ 20%). Text color: `primary`.
*   **Tertiary:** Text-only with a 2px underline that expands on hover.

### Product Cards
*   **Rule:** Forbid divider lines. 
*   **Style:** Use `surface-container-lowest` (#ffffff). Corner radius `lg` (1rem). 
*   **Spacing:** Use `spacing-4` (1.4rem) internal padding. Imagery should be flush to the top with a subtle 2% scale-up animation on hover.

### Input Fields
*   **Style:** Minimalist. No background fill—use a `Ghost Border` at the bottom only, or a very soft `surface-container-high` fill with no border.
*   **Focus State:** The bottom border transforms into `primary` (#004253) with a 2px thickness.

### Chips & Filters
*   **Selection Chips:** Use `secondary_container` (#d4e5ef) for unselected and `primary` (#004253) for selected.
*   **Shape:** Always `full` (pill-shaped) to contrast against the `md` roundedness of cards.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. For example, a hero image may take up 7 columns of a 12-column grid, while the text occupies 4 columns with a 1-column gap.
*   **Do** use `spacing-12` (4rem) or `spacing-16` (5.5rem) between major sections to let the design "breathe."
*   **Do** use high-quality, lifestyle-focused imagery with consistent art direction (warm lighting, soft shadows).

### Don't:
*   **Don't** use 100% black (#000000) for text. Always use `on-surface` (#191c1d) to maintain tonal softness.
*   **Don't** use "Drop Shadows" on text. If text is over an image, use a subtle `surface-dim` gradient overlay behind the text.
*   **Don't** use divider lines between list items. Use a background color shift or `spacing-3` (1rem) of vertical white space.
*   **Don't** crowd the CTA. Ensure every "Buy" button has at least `spacing-6` (2rem) of clear space around it.
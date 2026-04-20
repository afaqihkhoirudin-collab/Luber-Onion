# Design System Documentation: The Earth’s Ruby

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Botanical Gallery."** 

We are moving away from the "commodity grocery" aesthetic and toward a high-end editorial experience. Shallots are not just a vegetable; they are a premium, layered, and vibrant botanical ingredient. The design system leverages white space as a luxury and uses the deep, translucent reds of the shallot skin to create a sense of depth and sophistication. 

By breaking the traditional rigid grid with intentional asymmetry—such as overlapping product imagery and high-contrast typography scales—we create a digital storefront that feels more like a curated culinary magazine than a standard e-commerce platform.

---

## 2. Colors
Our palette is rooted in the rich, organic tones of the red shallot, balanced against a pristine, "Gallery White" foundation.

### The "No-Line" Rule
To maintain a premium feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined through:
- **Tonal Shifts:** Transitioning from `surface` (#faf9f8) to `surface_container_low` (#f4f3f2).
- **Negative Space:** Using the Spacing Scale to create "breathing room" that implies a change in context.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. Use the surface-container tiers to define importance:
- **Level 0 (Base):** `surface` (#faf9f8) for the main page background.
- **Level 1 (Sections):** `surface_container_low` (#f4f3f2) to define large content blocks.
- **Level 2 (Cards):** `surface_container_lowest` (#ffffff) to make product cards "pop" off a low-tier background.

### The "Glass & Gradient" Rule
For floating elements like navigation bars or quick-buy overlays, utilize **Glassmorphism**. Apply `surface` with 80% opacity and a `24px` backdrop-blur. 
*   **Signature Texture:** Main CTAs should use a subtle linear gradient from `primary` (#98001e) to `primary_container` (#bc2132) at a 135-degree angle. This adds a "soul" to the red that flat hex codes cannot achieve.

---

## 3. Typography
We use a dual-font strategy to balance character with utility.

*   **Display & Headlines (Plus Jakarta Sans):** These are our "Voice." They should be used with tight letter-spacing (-0.02em) and high contrast. The `display-lg` (3.5rem) should be used for hero statements to create an authoritative, editorial feel.
*   **Body & Labels (Be Vietnam Pro):** These are our "Engine." This typeface provides exceptional legibility at smaller scales. Use `body-md` (0.875rem) for product descriptions to maintain a refined, clean look.

**Hierarchy Tip:** Always pair a `display-sm` headline with a `label-md` in all-caps (tracked out +10%) to create the "magazine header" look.

---

## 4. Elevation & Depth
In this design system, depth is organic, not artificial.

*   **The Layering Principle:** Avoid shadows for static content. Instead, "stack" surface tiers. A `surface_container_lowest` card sitting on a `surface_container` background creates a natural lift.
*   **Ambient Shadows:** For interactive floating elements (e.g., Modals), use a shadow tinted with our `on_surface` color.
    *   *Spec:* `0px 12px 32px rgba(26, 28, 28, 0.06)`. 
    *   The low opacity (6%) ensures the shadow feels like ambient light hitting paper, not a digital drop-shadow.
*   **The Ghost Border:** If a boundary is required for accessibility, use `outline_variant` (#e3bebc) at **15% opacity**. This creates a "whisper" of a line that guides the eye without cluttering the UI.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary_container`. Corner radius: `full`. Text: `label-md` (bold, white).
*   **Secondary:** Ghost style. No background, `outline` token at 20% opacity. Text: `on_surface`.
*   **Tertiary:** Text-only with a `primary` #98001e underline that expands on hover.

### Product Cards
*   **Styling:** Forbid dividers. Use `surface_container_lowest` for the card body. 
*   **Imagery:** Use "organic" cropping—allow shallot roots or skins to slightly overlap the edge of the card container to break the "box" feel.

### Input Fields
*   **State:** Use `surface_container_high` for the background of the input area. 
*   **Corners:** `md` (0.75rem).
*   **Active State:** Transition the background to `surface` and add a `ghost border` using the `primary` color at 40% opacity.

### Selection Chips
*   **Filter Chips:** Use `surface_container_highest` with `on_surface_variant` text. When selected, switch to `primary` with `on_primary` text. No borders.

### Special Component: "The Harvest Badge"
*   A small, circular badge using `tertiary` (#00515f) for "In Stock" or "New Harvest" alerts. The deep teal provides a sophisticated contrast to the dominant reds.

---

## 6. Do's and Don'ts

### Do
*   **Do** use asymmetrical layouts. Place text on the left and allow product imagery to bleed off the right edge of the screen.
*   **Do** use `display-lg` typography for price points in a hero section—make the price a design element.
*   **Do** favor vertical white space. If you think there is enough space, add 24px more.

### Don't
*   **Don't** use 100% black (#000000). Always use `on_background` (#1a1c1c) for text.
*   **Don't** use standard "Drop Shadows." Use the Tonal Layering or Ambient Shadow specs provided.
*   **Don't** use divider lines between list items. Use a 4px background shift (`surface_container_low`) on hover instead.
*   **Don't** use "Alert Red" for errors if you can help it. Use the `error` (#ba1a1a) token, which is tuned to sit harmoniously with our primary shallot red.
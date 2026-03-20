# Design System Strategy: The Obsidian Gallery

## 1. Overview & Creative North Star
The Creative North Star for this design system is **"The Obsidian Gallery."** 

This system rejects the "service-provider" template in favor of a "curated exhibition." We treat every tattoo and piercing not as a commodity, but as a masterpiece housed within a high-end, dark-mode sanctuary. The aesthetic breaks the traditional rigid grid through **intentional asymmetry** and **tonal depth**, creating an edgy yet sophisticated atmosphere. 

By utilizing a "Museum Lighting" approach—where the background is nearly invisible and light is used only to highlight the art—we ensure the user’s focus remains on the craftsmanship. We move beyond standard UI by layering obsidian surfaces and using "Crimson" (`primary`) and "Gold" (`secondary`) as surgical strikes of color that guide the eye to calls-to-action and critical details.

## 2. Colors: Depth over Definition
The palette is rooted in the absence of light, using deep charcoals and obsidian tones to create a sense of infinite space.

*   **Core Tones:** The `background` (#0e0e0e) and `surface` (#0e0e0e) act as the canvas. 
*   **The "No-Line" Rule:** Under no circumstances are 1px solid borders to be used for sectioning content. Boundaries must be defined through background shifts. A section might move from `surface` to `surface-container-low` (#131313) to denote a change in context.
*   **Surface Hierarchy & Nesting:** Use the `surface-container` tiers to create a physical sense of stacking. 
    *   *Hero Section:* `surface-background`
    *   *Featured Artist Card:* `surface-container-low`
    *   *Nested Detail/Price Chip:* `surface-container-high`
*   **The Glass & Gradient Rule:** For floating navigation or modal overlays, use "Glassmorphism." Apply `surface-container` colors at 70% opacity with a `backdrop-blur` of 20px. 
*   **Signature Textures:** For primary CTAs, do not use flat fills. Apply a subtle linear gradient from `primary` (#ff8d8c) to `primary-container` (#ff7576) at a 45-degree angle to give buttons a "living" velvet-like glow.

## 3. Typography: The Editorial Contrast
We employ a high-contrast typographic pairing to balance "The Raw" (Art) with "The Refined" (Professionalism).

*   **The Stylistic Serif (Newsreader):** Used for `display` and `headline` levels. This font carries the "Editorial" weight, appearing like a high-end fashion magazine. It conveys history, needles, and precision.
*   **The Technical Sans (Manrope & Space Grotesk):** Used for `body` and `label` levels. These provide a clean, modern counterpoint that ensures legibility for pricing, care instructions, and artist bios.
*   **Hierarchy as Identity:** Large `display-lg` headings should often be placed with negative letter-spacing (-0.02em) and occasionally offset from the grid to create an edgy, "zine-like" feel. Use `label-md` in `secondary` (Gold) for "New" or "Exclusive" tags to mimic a gallery plaque.

## 4. Elevation & Depth: Tonal Layering
Traditional shadows and borders are forbidden. Depth is a matter of light hitting obsidian surfaces.

*   **The Layering Principle:** To lift an element, move it up the token scale (e.g., a `surface-container-highest` card sitting on a `surface-dim` background). This creates a "soft lift" that feels premium rather than "pasted."
*   **Ambient Shadows:** If a floating effect is required (e.g., a lightbox for a tattoo portfolio), use a massive blur (60px+) with an extremely low-opacity shadow (#000000 at 15%). It should feel like an object casting a shadow in a dimly lit room, not a digital drop-shadow.
*   **The "Ghost Border" Fallback:** If a container requires a border for accessibility, use `outline-variant` at 15% opacity. It should be felt, not seen.
*   **Asymmetric Overlaps:** Break the "box" feel by having images (tattoos) overlap from a `surface-container-low` section into a `surface` section. This creates a sense of physical layering.

## 5. Components

### Buttons
*   **Primary:** A sharp-edged (`0px` radius) block using the Crimson gradient. Text is `on-primary-fixed` (Black) for maximum punch.
*   **Secondary:** Ghost-style. No fill, `outline` token at 30% opacity, with `secondary` (Gold) text. On hover, the background fills with a 5% `secondary` tint.
*   **Tertiary:** Text-only in `primary-dim`, underlined with a 1px `primary` line that expands on hover.

### Cards (The "Gallery Frame")
*   **Construction:** No borders. Background is `surface-container-lowest`. 
*   **Imagery:** Images should be high-contrast. On hover, the image should subtly scale (1.05x) while the background container remains static.
*   **Content:** Typography is left-aligned with significant `12` (4rem) padding to give the art "room to breathe."

### Inputs & Fields
*   **Styling:** Bottom-border only (`outline-variant`). When focused, the border transitions to `primary` (Crimson) and the label (using `label-sm`) floats upward. 
*   **Error State:** Use `error` (#ff6e84) for text and `error_container` for a subtle 5% background wash within the input field.

### Portfolio Chips
*   **Style:** Small, `0px` radius tags using `surface-container-highest`. Text in `on-surface-variant`. Used to categorize styles (e.g., "Blackwork," "Traditional," "Micro-realism").

### Portfolio Lists
*   **The "No Divider" Rule:** Never use lines to separate list items. Use a `10` (3.5rem) vertical spacing scale gap. If separation is visually required, use alternating backgrounds between `surface` and `surface-container-low`.

## 6. Do's and Don'ts

### Do:
*   **DO** use whitespace (using the `20` and `24` spacing tokens) aggressively. In a gallery, the space around the art is as important as the art itself.
*   **DO** use `0px` border radius for everything. Sharp corners convey the "edge" and "needle" aspect of the industry.
*   **DO** use the `secondary` (Gold) sparingly—only for high-value items like "Book Now" or "VIP Artist."

### Don't:
*   **DON'T** use rounded corners. It softens the brand and makes it feel like a generic tech app.
*   **DON'T** use 100% white (#FFFFFF) for long-form body text; use `on-surface-variant` (#adaaaa) to reduce eye strain on the dark background.
*   **DON'T** use standard "Material Design" shadows. They are too "software-centric" for an artistic, editorial experience.
# Design System Specification: The Academic Architect

## 1. Overview & Creative North Star
**Creative North Star: The Scholarly Sanctuary**
This design system moves away from the "chat bubble" clutter of standard bots, transforming the IELTS preparation journey into a high-end, editorial experience. We are not just building a utility; we are building a digital tutor that feels authoritative yet breathable. 

The aesthetic is driven by **"Structured Serenity."** We break the rigid, boxy constraints of mobile interfaces by using intentional asymmetry in data visualization and overlapping typographic elements. By prioritizing white space (breathing room) and tonal depth over harsh lines, we create an environment that reduces cognitive load—essential for high-stakes exam preparation.

---

## 2. Colors & Surface Philosophy
The palette is rooted in `primary` (#002c98), conveying deep academic trust, balanced by `secondary` (#1b6d24) to signal success and growth.

### The "No-Line" Rule
**Explicit Instruction:** You are prohibited from using 1px solid borders to define sections. All separation must be achieved through:
- **Tonal Shifts:** Placing a `surface-container-low` component on a `surface` background.
- **Negative Space:** Using generous padding to define boundaries.
- **Glassmorphism:** Floating elements using `surface` colors at 80% opacity with a `20px` backdrop-blur to create an "intellectual layer."

### Surface Hierarchy & Nesting
Treat the interface as a physical desk with stacked sheets of fine vellum.
1.  **Base Layer:** `surface` (#f8f9ff) – The expansive "canvas."
2.  **Sectional Layer:** `surface-container-low` (#eef4ff) – Defines broad content areas (e.g., a lesson module).
3.  **Active Component Layer:** `surface-container-lowest` (#ffffff) – Used for primary cards or input areas to make them "pop" against the canvas.
4.  **Interactive Layer:** `surface-container-highest` (#dde3ee) – Reserved for pressed states or secondary metadata backgrounds.

### Signature Textures
Avoid flat primary blocks. Use linear gradients for hero stats and progress trackers: 
- `primary` (#002c98) → `primary-container` (#1a43bf) at a 135-degree angle. This adds "soul" and a sense of forward momentum.

---

## 3. Typography: The Editorial Voice
We use a tri-font system to establish a clear cognitive hierarchy.

*   **The Authority (Display/Headline):** **Manrope.** Used for scores and section starts. Its geometric clarity feels modern and precise.
    *   *Display-LG (3.5rem):* For Band Scores (e.g., "7.5").
    *   *Headline-MD (1.75rem):* For lesson titles.
*   **The Narrative (Title/Body):** **Public Sans.** A neutral, high-legibility typeface designed for long-form reading and academic comprehension.
    *   *Body-LG (1rem):* Standard lesson text. Line height should be 1.6x for readability.
*   **The Data (Labels):** **Inter.** A functional workhorse for metadata and progress indicators.
    *   *Label-MD (0.75rem):* For "Time Remaining" or "Word Count."

---

## 4. Elevation & Depth
In this system, depth is a tool for focus, not just decoration.

*   **The Layering Principle:** To highlight a "Daily Goal" card, do not use a border. Place a `surface-container-lowest` card on top of a `surface-container` background.
*   **Ambient Shadows:** For floating action buttons or modal components, use a "Scholar’s Shadow":
    *   `X: 0, Y: 8px, Blur: 24px, Spread: -4px`
    *   Color: `on-surface` (#161c24) at **6% opacity**. It should feel like a soft glow of light, not a "drop shadow."
*   **The Ghost Border:** If high-contrast accessibility is required, use `outline-variant` at **15% opacity**.

---

## 5. Components

### High-Fidelity Lesson Cards
*   **Structure:** No dividers. Use `surface-container-low` backgrounds.
*   **Progress:** Use a `secondary` (#1b6d24) thin progress bar (4px) at the very top of the card, bleeding edge-to-edge.
*   **Corner Radius:** Use `xl` (1.5rem) for external cards to feel approachable.

### Buttons (The "Call to Action")
*   **Primary:** `primary` background with `on-primary` text. Radius: `full`. Use a subtle gradient to `primary-container`.
*   **Secondary:** `surface-container-high` background with `primary` text. No border.
*   **Tertiary:** Text-only in `primary` with `label-md` uppercase styling for "Skip" or "Back."

### Data Visualization (IELTS Stats)
*   **The "Progress Pulse":** Instead of a standard bar, use a soft `secondary_container` track with a `secondary` fill. 
*   **Anomalies:** Use `error` (#ba1a1a) only for critical errors in grammar exercises; otherwise, use `primary_fixed` to highlight areas for improvement without being discouraging.

### Input Fields
*   **Style:** `surface-container-lowest` background. 
*   **Focus State:** Do not change the border color. Instead, shift the background to `surface-container-low` and add a subtle `primary` ambient shadow (4% opacity).

---

## 6. Do’s and Don’ts

### Do
*   **Do** use `secondary` (#1b6d24) and its variants (`secondary_fixed`) to celebrate small wins—finishing a paragraph or learning a new word.
*   **Do** allow the `background` to breathe. If in doubt, add 8px more padding.
*   **Do** use `title-lg` for question prompts to give them editorial weight.

### Don’t
*   **Don’t** use 1px dividers. If you need to separate content, use a 12px vertical gap or a subtle background shift to `surface-container-low`.
*   **Don’t** use pure black (#000000). Use `on-surface` (#161c24) for all text to maintain the sophisticated "Deep Blue/Grey" academic tone.
*   **Don’t** use "Alert" reds for "Incorrect" answers. Use `error_container` with `on-error-container` text to keep the student in a "growth mindset" rather than a "failure mindset."
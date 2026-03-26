```markdown
# Design System Document

## 1. Overview & Creative North Star: "The Obsidian Archive"

This design system is built to honor the legacy of the PlayStation 3 era while reframing it through a sophisticated, modern lens. We are moving away from the skuomorphic gloss of 2006 and toward a **"High-End Editorial"** experience.

**The Creative North Star: The Obsidian Archive.**
Imagine a physical gallery where artifacts are suspended in deep, dark space, illuminated only by the soft glow of blue light and the refracted edges of glass. This system breaks the "template" look by utilizing **intentional asymmetry**—offsetting game titles from their thumbnails—and a **high-contrast typography scale** that treats game metadata like a luxury fashion magazine. We do not use grids to cage content; we use light and depth to guide the eye.

---

## 2. Colors: Depth Beyond Black

The palette is rooted in `surface_container_lowest` (#0e0e0e) to provide a true "infinite" dark background, allowing the vibrant `tertiary` (#00daf8) neon accents to vibrate against the darkness.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning. Boundaries must be defined solely through background color shifts. 
- *Example:* A game description section (`surface_container_low`) sitting on a main page background (`surface`).
- *Why:* Solid lines feel like "bootstrap" templates. Tonal transitions feel like "custom architecture."

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers of frosted glass.
- **Base Layer:** `surface` (#131313)
- **Primary Layout Containers:** `surface_container` (#201f1f)
- **Interactive Cards/Floating Elements:** `surface_container_high` (#2a2a2a)
- **Pop-overs/Modals:** `surface_container_highest` (#353534)

### The "Glass & Gradient" Rule
To achieve the premium "legacy" feel, use **Glassmorphism** for navigation bars and hovering game cards.
- **Glass Formula:** Background color at 60% opacity + `backdrop-blur: 24px`.
- **Signature Textures:** Use a subtle radial gradient transitioning from `primary_container` (#0021a7) to `surface` at 0% opacity in the corners of hero sections to simulate the nostalgic "glow" of the original XMB interface.

---

## 3. Typography: The Futuristic Editorial

We pair the technical precision of **Space Grotesk** with the humanist clarity of **Inter**.

- **Display (Space Grotesk):** Used for game titles and major headlines. Set these with "tight" letter-spacing (-2%) to create a modern, high-fashion look.
- **Body (Inter):** Used for descriptions and technical specs. Inter provides a neutral "anchor" to the more aggressive Display font.
- **Hierarchy as Identity:** Use `display-lg` (3.5rem) for hero titles, but immediately follow it with `label-md` (0.75rem) for metadata (e.g., RELEASE YEAR | STUDIO). This extreme jump in scale creates an "editorial" rather than "functional" feel.

---

## 4. Elevation & Depth: Tonal Layering

Traditional shadows are too "web-standard" for this experience. We use light to create lift.

- **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` section. The slight shift in value creates a "recessed" or "lifted" effect that is felt rather than seen.
- **Ambient Shadows:** When a game card must "float" during a hover state, use a shadow with a 40px blur at 8% opacity. The shadow color should be `primary` (#bbc3ff) to mimic the way a blue neon light would cast a shadow in a dark room.
- **The "Ghost Border" Fallback:** If a container requires definition against a complex background image, use a "Ghost Border": `outline_variant` (#444652) at **15% opacity**. Never use a 100% opaque border.
- **Neon Glows:** For "Active" states (e.g., the selected game), use a 2px outer glow using `tertiary` (#00daf8) with a 15px spread. This mimics the "glow" of a CRT or power indicator.

---

## 5. Components

### Cards & Lists (Game Catalog)
- **Execution:** Forbid the use of divider lines. 
- **Spacing:** Use `spacing-8` (2.75rem) to separate catalog categories. 
- **Style:** Cards should use a vertical aspect ratio (2:3) to mimic physical game cases. Use `roundedness-lg` (0.5rem) for a modern, slightly softened edge.

### Buttons
- **Primary:** Gradient fill from `primary` (#bbc3ff) to `inverse_primary` (#1a41ff). Text should be `on_primary_fixed` (#000e5e).
- **Secondary (Glass):** Semi-transparent `surface_variant` with a `backdrop-blur`. This allows the game's background art to peek through the UI.
- **Tertiary:** Text-only using `tertiary` (#00daf8) for "Back" or "Cancel" actions.

### Interactive "Power" Chips
- Used for game genres (e.g., "RPG," "Action").
- **Style:** Solid `surface_container_highest` background with a `tertiary` (#00daf8) 2px left-side accent line. No right, top, or bottom borders.

### Input Fields
- **Style:** Underline-only style. No boxed inputs. Use `outline` (#8e909d) for the underline, which transitions to `tertiary` (#00daf8) on focus with a soft bottom-glow.

---

## 6. Do's and Don'ts

### Do:
- **Use Asymmetry:** Offset text from images. Let the typography "breathe" into the negative space.
- **Embrace the Dark:** Use `#0a0a0a` for the deepest backgrounds; it makes the high-quality game imagery "pop."
- **Layer Glass:** Stack semi-transparent elements to create a sense of physical history and depth.

### Don't:
- **Don't use 1px Borders:** It breaks the "Obsidian" illusion and makes the UI look like a table or spreadsheet.
- **Don't use Pure White:** Use `on_surface` (#e5e2e1) for text. Pure white (#ffffff) is too harsh and ruins the cinematic atmosphere.
- **Don't Overuse Glows:** A glow should signify a "Power On" state or a "Selected" state. If everything glows, nothing is important.

### Accessibility Note:
While we utilize deep blacks and subtle grays, ensure that all `body-md` text maintaining a contrast ratio of at least 4.5:1 against its specific `surface-container` tier. Use `on_surface` for all primary reading material.
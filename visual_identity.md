# PARANOID AND READY
## Brand Visual Identity AND Voice Guide

*Last updated: March 2026 | For use with: designers, developers, AI agents, copywriters*

---

## Core Aesthetic

Cold Bureaucracy. Classified Document. Concrete Bunker.

The visual identity communicates seriousness through restraint. The design should feel like a declassified government brief: dense with information, zero decoration, slightly uncomfortable to ignore. Not military cosplay. Not survivalist fantasy. A document that looks like it was typed on a cold desk in a building with no windows.

Information is the product. Everything visual serves clarity. No rounded corners. No softness. No stock photo warmth.

---

## Color Palette

| Role | Hex | Name | Usage |
|---|---|---|---|
| Background | `#C5C5C5` | Concrete Grey | Primary background |
| Surface | `#B8B8B8` | Worn Concrete | Raised sections, own-section panels |
| Surface Raised | `#AEAEAE` | Deep Concrete | Hover states on surfaces |
| Red | `#8B0000` | Dried Blood | Headers, category names, tags, spec data, accents |
| Red glow | `rgba(139,0,0,0.07)` | | Hover background on accordion triggers |
| Ink | `#1A1A1A` | Ink Black | Primary text, borders, buttons |
| Ink mid | `#3A3A3A` | | Secondary text, descriptions in "why" columns |
| Ink light | `#555555` | | Muted text, metadata, timestamps |
| White | `#FFFFFF` | | Button text on ink backgrounds, unit toggle active text |
| Border | `#1A1A1A` | | All container borders, type sections, header line |
| Border mid | `#888888` | | Subtle dividers within panels, row separators |

**Hard rule: buttons are ink black background with white text. Hover state is dried blood red background with white text.**

**Hard rule: spec data lines (type-spec) are always `#8B0000` dried blood red. Both the bold value and the label text.**

---

## Typography

### JetBrains Mono (single typeface)

The entire site uses one font family: JetBrains Mono. No secondary typeface. The monospace consistency reinforces the bureaucratic, technical document feel.

**Google Fonts import:** `JetBrains+Mono:wght@400;500;600;700;800`

| Element | Weight | Size | Spacing | Case |
|---|---|---|---|---|
| Body text | 400 | 16px | -0.01em | Sentence |
| Line height (body) | | | 1.6 | |
| Headers (h1) | 800 | clamp(22px, 3.5vw, 38px) | 2px | UPPERCASE |
| Subcategory names | 800 | 13px | 2px | UPPERCASE |
| Type names | 800 | 11px | 2px | UPPERCASE |
| Type descriptions | 400 | 14px | -0.01em | Sentence |
| Type specs | (any) | 10px | 0.5px | Sentence |
| Tags | 700 | 9px | 1px | UPPERCASE |
| Nav links | 500 | 10px | 1.5px | UPPERCASE |
| Buttons | 700 | 10px | 2px | UPPERCASE |
| Logo | 800 | 13px | 3px | UPPERCASE |
| Breadcrumbs | 500 | 10px | 1px | UPPERCASE |
| Section labels | 800 | 10px | 3px | UPPERCASE |

The tight letter-spacing on body text (-0.01em) creates a subtle urgency. Headers use wide tracking (2px+) for authority.

---

## Logo

The logo is three separate words: **PARANOID AND READY**

- PARANOID: JetBrains Mono, weight 800, uppercase, dried blood red (`#8B0000`)
- AND: JetBrains Mono, weight 800, uppercase, ink black (`#1A1A1A`), `.logo-and` class
- READY: JetBrains Mono, weight 800, uppercase, dried blood red (`#8B0000`)

Spaces between all three words. Letter-spacing: 3px. Font size in nav: 13px.

**HTML:** `PARANOID <span class="logo-and">AND</span> READY`

---

## Ampersands

There are no ampersands anywhere on the site. All instances of "&" are replaced with the word "AND" in uppercase. This applies to:

- Category names: "Energy AND Power", "Water AND Hydration"
- Subcategory names: "Chemical AND UV Purification"
- Breadcrumbs, page titles, everywhere

The `.cat-amp` CSS class is retired. No italic Georgia ampersands.

---

## Container and Layout System

Max width: `1000px`, centered, with `48px` horizontal padding (24px on mobile). Both values are set as CSS custom properties (`--max-w`, `--pad`) so every element references the same constraints.

**Everything uses the same container width:** nav, header line, content sections, dividers, footer. Nothing bleeds wider than the container. The page scales fluidly from phone to desktop.

**Section dividers** are `<hr class="divider">` elements placed **inside** `.container` divs, not `border-top` on section elements. This ensures dividers align with content edges at all widths.

**Nav is the grid itself** (no `.nav-inner` wrapper). The `<nav>` element uses `max-width: var(--max-w)` and `padding: 28px var(--pad) 0` directly.

---

## Nav

The `<nav>` element is the grid itself (three-column: left links | center logo | right search + toggle). No wrapper div inside. Uses the same `--max-w` and `--pad` as all containers.

- Header line below nav: `<hr>` inside a `.header-line` div that uses the same max-width and padding
- Search placeholder: `"Search..."` (consistent across all pages)
- Nav link labels: "Categories", "Guides" (no "Gifts" link in nav)
- On mobile: nav-left hides, grid collapses to `auto 1fr` (logo left, search right)

---

## Page Structure: Category Pages

1. Breadcrumb
2. Hero: page title in dried blood red, intro paragraph in ink black
3. Subcategory accordion list (each ending with "What to own" section)
4. CTA block
5. Related Guides
6. Footer

---

## Subcategory Accordion

- Top and bottom borders: `2px solid #1A1A1A` (ink black)
- First item also gets a top border
- Trigger text: JetBrains Mono, 13px, weight 800, uppercase, dried blood red, letter-spacing 2px
- Open/close icon: `+` rotates 45deg to form `x` on open. Ink black color.
- Hover state: subtle red glow background

---

## Type Sections (within accordions)

- Border: `1px solid #1A1A1A`
- Background: `rgba(197, 197, 197, 0.3)`, hover lifts to `rgba(184, 184, 184, 0.6)`
- Type name: 11px, weight 800, uppercase, ink black, letter-spacing 2px
- Type tag: 9px, weight 700, uppercase, dried blood red text, dried blood red border
- Description: 14px, weight 400, ink black
- Specs row: 10px, **dried blood red** (both bold values and label text)

---

## What to Own Section

Appears at the bottom of each subcategory accordion, after all type sections.

- Background: `#B8B8B8` (worn concrete surface)
- Left border: 3px solid dried blood red
- Label: "WHAT TO OWN" in 9px, weight 800, letter-spacing 3px, dried blood red
- Two-column CSS grid: left 240px fixed (what), right flexible (why)
- What column: 13px, weight 600, ink black
- Why column: 13px, weight 400, ink mid (`#3A3A3A`)
- Row dividers: `1px solid #888888`
- Last row has no bottom border

**Content rule:** every item on the left must have a matching explanation on the right. Never list something without saying why it belongs.

---

## CTA Block

- Separated from content above by `<hr class="divider">` inside the container
- Title: 16px, weight 800, uppercase, ink black, letter-spacing 2px
- Description: 14px, weight 400, ink mid
- Button: ink black background, white text, hover goes to dried blood red background

---

## Related Guides

- Separated from content above by `<hr class="divider">` inside the container
- Section label: 10px, weight 800, dried blood red, uppercase, with right-extending ink line
- Article rows bordered with `#888888`
- Tag: 9px, weight 700, dried blood red
- Timestamp: 9px, ink light
- Title: 14px, weight 600, ink black
- Excerpt: 13px, weight 400, ink mid
- Read link: 10px, weight 700, dried blood red, uses `+` not arrows

---

## Footer

- Separated from content above by `<hr class="divider">` inside the container (not `border-top` on `<footer>`)
- Uses `.container` (not `.footer-inner`)
- Brand logotype: same as nav logo (PARANOID AND READY, red/ink/red)
- Nav links: 10px, weight 500, ink mid, hover ink black
- Bottom row: tagline (italic, ink mid) | copyright (11px, ink light)
- Bottom row separated by `#888888` border
- Footer nav: "About" and "Contact" only

---

## Unit Toggle

A compact toggle in the nav right area switches between imperial (LB) and metric (KG).

- Border: `1px solid #1A1A1A`
- Active state: ink black background, white text
- Inactive: transparent background, ink light text

**Scope:** the toggle must apply to ALL measurements on the page. Every gallon, ounce, pound, mile, and degree Fahrenheit must be wrapped in `data-imperial` and `data-metric` HTML attributes. This includes prose text, type-spec values, type-name headings, and own-what labels. No measurement with a unit is ever hardcoded as plain text.

---

## Paper Grain Effect

A subtle SVG noise filter is applied as a fixed overlay on the body:

```css
body::before {
  content: '';
  position: fixed;
  inset: 0;
  background-image: url("data:image/svg+xml,...noise SVG...");
  pointer-events: none;
  z-index: 9999;
  opacity: 0.6;
}
```

This creates a photocopy/concrete paper texture. The opacity (0.6) is calibrated for the concrete grey background. Adjust down if moving to a lighter background.

---

## Photography and Imagery

### What to use

- Real gear on real surfaces: concrete, wood, metal, fabric, field conditions.
- Functional compositions: gear laid flat, gear in use, gear in context.
- Natural and low-key lighting. Moody is fine, dramatic is fine. Stock-bright is not.
- Close-ups of specs, ports, dials, materials.

### What to avoid

- Studio-white backgrounds. No floating products on pure white.
- Stock lifestyle photography: smiling families, posed hikers.
- Military or tactical imagery unless the product is genuinely tactical.
- Disaster photography or fear imagery.
- AI-generated imagery that looks synthetic or uncanny.

---

## Voice Rules (Hard)

### NEVER use em dashes (the long dash)

This is a hard rule with no exceptions, anywhere on the site, in any content type. Em dashes are a known AI writing tell and break the voice.

**Instead use:** a colon, a new sentence, a comma, or parentheses (rare).

### NEVER use exclamation marks

The content should carry its own energy.

### NEVER use AI-voice filler phrases

"Let's dive in", "It's worth noting", "In conclusion", "Without further ado", "In today's world", "Genuinely", "Honestly", "Straightforward", "Game-changer"

### Tone: calm, practical, slightly wry

Not panicked. Not casual either. There is an underlying current of "you should probably get around to this." The voice is self-aware: it knows the subject matter is a little intense, and it is comfortable with that.

### Sentence structure

Short and varied. Mix punchy fragments with longer explanatory sentences. Read it out loud. If it sounds like a textbook, break it up.

### Specificity

Always use real numbers, real specs, real-world context. No "this is great for emergencies." Say "charges a phone 16 times and runs a mini fridge for 4 hours."

### Honesty

Always include trade-offs. No product is perfect. If it has a flaw, name it.

### Brevity

If you have made the point, stop.

### Political neutrality

Prepare for scenarios, not ideologies.

---

## Words and Phrases

| Instead of... | Use... |
|---|---|
| When SHTF | In an emergency / when things go wrong |
| Bug out bag | Go-bag / emergency bag |
| Must-have / essential | Worth stocking / smart to have |
| Game-changer | (Just describe what it does) |
| & | AND |
| The long dash | A colon, comma, or new sentence |
| Let's dive in | (Delete) |
| It's worth noting | (Delete. Just note it.) |

---

## Quick Reference for AI Agents

- **Palette:** concrete grey bg, ink black text, dried blood red headers/specs/accents
- **Font:** JetBrains Mono only. Single typeface, no secondary font.
- **Logo:** PARANOID AND READY. Three words, spaced. Red/ink/red.
- **Ampersands:** none. Always "AND" in uppercase.
- **Em dashes:** never. Not in copy, not in specs, not anywhere.
- **Buttons:** ink black fill, white text. Hover: dried blood red fill, white text.
- **Specs:** always dried blood red (#8B0000), both values and labels.
- **Unit toggle:** must cover ALL measurements. data-imperial/data-metric on every value.
- **Search bar:** placeholder text is "Search..." on every page.
- **Container:** 1000px max-width, 48px padding (24px mobile). All via CSS variables `--max-w` and `--pad`.
- **Dividers:** `<hr class="divider">` inside `.container` divs. Never `border-top` on section elements.
- **Borders:** 1px solid ink black for sections, 2px solid ink black for major divisions.
- **No rounded corners anywhere.**
- **Styling Architecture:** All CSS lives in `/css/style.css`. Absolutely no inline `<style>` tags in HTML.
- **Tone:** calm, practical, slightly wry. Never panicked, never salesy.

---

*Stay prepared. Not surprised.*

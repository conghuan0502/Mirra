---
name: Mirra
description: A loud cobalt sticker-sheet landing for an experimental Hackintosh iPhone Mirroring companion.
colors:
  blue: "#1e40af"
  blue-deep: "#0f2a47"
  periwinkle: "#abbaff"
  ice: "#c3efff"
  acid-lime: "#eff35f"
  white: "#ffffff"
  ink: "#1a1a1a"
  sheet: "#f9fafb"
typography:
  display:
    fontFamily: "Archivo Variable, system-ui, sans-serif"
    fontSize: "clamp(3.4rem, 12.4vw, 10.5rem)"
    fontWeight: 900
    lineHeight: 0.86
    letterSpacing: "-0.03em"
    fontVariation: "font-stretch 118%"
  headline:
    fontFamily: "Archivo Variable, system-ui, sans-serif"
    fontSize: "1.6rem"
    fontWeight: 900
    lineHeight: 1
    letterSpacing: "-0.02em"
    fontVariation: "font-stretch 118%"
  title:
    fontFamily: "Archivo Variable, system-ui, sans-serif"
    fontSize: "1.1rem"
    fontWeight: 800
    lineHeight: 1.1
  body:
    fontFamily: "Archivo Variable, system-ui, sans-serif"
    fontSize: "1.05rem"
    fontWeight: 500
    lineHeight: 1.5
    fontVariation: "font-stretch 100%"
  label:
    fontFamily: "Archivo Variable, system-ui, sans-serif"
    fontSize: "0.85rem"
    fontWeight: 700
    lineHeight: 1.35
rounded:
  pill: "99px"
  card: "1.75rem"
  shot: "2rem"
  sheet: "3.5rem"
spacing:
  grid-cell: "4rem"
  sm: "0.5rem"
  md: "1rem"
  lg: "1.5rem"
  xl: "3rem"
components:
  pill-outline:
    backgroundColor: "transparent"
    textColor: "{colors.white}"
    rounded: "{rounded.pill}"
    padding: "0.45rem 1rem"
  pill-outline-hover:
    backgroundColor: "rgb(255 255 255 / 0.14)"
  pill-solid-hover:
    backgroundColor: "{colors.white}"
    textColor: "{colors.blue}"
  tag-status:
    backgroundColor: "{colors.acid-lime}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "0.45rem 0.8rem"
  brand-plate:
    backgroundColor: "{colors.white}"
    textColor: "{colors.ink}"
    padding: "0.35rem 0.8rem 0.35rem 0.4rem"
  notice-bar:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.white}"
    padding: "0.55rem 1rem"
  device-card:
    backgroundColor: "rgb(15 42 71 / 0.5)"
    textColor: "{colors.white}"
    rounded: "{rounded.card}"
    padding: "1rem"
    width: "9.5rem"
  device-card-selected:
    backgroundColor: "{colors.acid-lime}"
    textColor: "{colors.ink}"
  route-tab-selected:
    backgroundColor: "{colors.acid-lime}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: "0.5rem 1rem"
  badge-action:
    backgroundColor: "{colors.acid-lime}"
    textColor: "{colors.ink}"
    rounded: "50%"
    size: "9rem"
  sheet:
    backgroundColor: "{colors.sheet}"
    textColor: "{colors.ink}"
    rounded: "{rounded.sheet}"
    padding: "4rem 2.5rem 2.5rem"
  screenshot-frame:
    backgroundColor: "{colors.ink}"
    rounded: "{rounded.shot}"
    padding: "1rem 1rem 0.5rem"
---

# Design System: Mirra

## Overview

**Creative North Star: "The Sticker Sheet"**

Mirra's landing is a loud blue field covered in things stuck onto it: tilted frosted device cards, a hand-drawn lime route arrow, a spinning circular badge, and display type that looks cut out and extruded. A near-white rounded sheet rises from the bottom edge like a second layer of paper. It is a user-pinned reference direction (blue, lime, white, extruded display type), built in code and adapted for Mirra's story: two devices, one bridge, an experimental tool.

The system is flat color with hard, saturated contrast. Primary blue is the ground, acid lime marks the one action and every selected state, white and pale ice carry the type tiers, ink sits on lime and white. Depth comes from the hard extruded display type and soft drop shadows under physically "stuck-on" objects. Motion is expressive on entry (expo-out) and quiet at rest; on a fine pointer the page also answers the hand: the objects lean, the controls pull toward the cursor, and the extrude's light follows it.

**Key Characteristics:**
- Blue ground with a faint 4rem periwinkle line grid (16% opacity).
- Lime is scarce and meaningful: action, selection, status, focus, pointer.
- Extra-bold, expanded Archivo in uppercase for display; normal-width Archivo for everything else.
- Everything interactive is a pill or a disc; nothing is a sharp rectangle.
- Tilted objects straighten on hover, focus, or selection.
- A pointer layer (trailing ring, parallax, magnetic pull, light-following extrude) that exists only on fine pointers without reduced-motion.

## Colors

A poster palette on one blue: blue, lime, white, ice, a deep-navy shadow, and near-black ink, with periwinkle for the grid.

### Primary
- **Primary Blue** (#1e40af): page background, theme color, hover text on the solid pill, and the cursor ring and dot when over the sheet.
- **Acid Lime** (#eff35f): the primary action badge, status tag, selected card and tab, first display line, route arrow, focus ring, text selection, scrollbar thumb, and the cursor ring and dot on the blue ground.

### Secondary
- **Deep Navy** (#0f2a47): the extruded depth behind display type, scrollbar track, frosted card fill (50%) and the tint of every drop shadow. Never a text or content fill color.

### Tertiary
- **Periwinkle** (#abbaff): the background grid lines only (16% opacity).
- **Ice** (#c3efff): the third display line and the lede; the 50% border on frosted cards.

### Neutral
- **Paper White** (#ffffff): second display line, outline borders, brand plate, body text on blue.
- **Sheet Mist** (#f9fafb): the rising sheet's background.
- **Ink** (#1a1a1a): all text on lime and white and the sheet, the notice bar, the screenshot frame, the focus ring on the sheet. Translucent ink (78% and 14%) carries sheet secondary text and dividers.

### Named Rules
**The One Action Rule.** Lime marks the single primary action (the circular badge) plus selected/active states, the experimental status, and pointer feedback. Lime never decorates; if it is not an action, a selection, a status, or the cursor, it is not lime.

**The Ink-On-Lime Rule.** Text on lime is always ink, never white. Text on blue is white or ice, never lime except display line one and arrows.

**The Ice Tier Rule.** Ice (#c3efff) is the quiet cool tier on blue: the last display line and the lede. It is not used on the sheet, on controls, or as a fill.

## Typography

**Display Font:** Archivo Variable (self-hosted via @fontsource-variable/archivo, width axis), fallback system-ui, sans-serif
**Body Font:** Archivo Variable at normal width (100%)

**Character:** One family, two voices. Expanded (118%) black-weight uppercase is the shout; normal-width medium is the explanation. Tight negative tracking and line-height under 1 make the display lines stack like a block of lettering.

### Hierarchy
- **Display** (900, clamp(3.4rem, 12.4vw, 10.5rem) for the largest line, 118% width, 0.86 line-height, -0.03em, uppercase): the three-line tagline. Lines step down in size and are staggered left, center, right: lime line (max 5.4rem), white middle (max 10.5rem), ice last (max 7.4rem).
- **Headline** (900, 1.6rem, 118% width, 1, uppercase): sheet section heading; brand wordmark at 0.95rem, 112% width.
- **Title** (800, 0.95rem to 1.1rem, 1.1): device card titles and requirement terms.
- **Body** (500, 1.05rem, 1.5, balanced wrap, max 34rem): ice lede and white route panel; sheet text at 0.9 to 0.95rem, max 44ch.
- **Label** (600 to 800, 0.72 to 0.85rem): pills, tabs, tag (uppercase, 0.06em tracking), card hints (underlined). The cursor's "GET" label is 0.5rem 900 uppercase.

### Named Rules
**The Two Widths Rule.** Expanded width is reserved for uppercase black-weight display and headings. Running text stays at normal width.

## Layout

A single centered column. Nav and hero are capped at 90rem; the hero stage at 68rem; the sheet grid at 72rem. A full-width ink notice bar tops the page. The hero is a flex column that centers the display type, with floating objects absolutely positioned off its corners (cards at the left and right edges, badge bottom right) with negative offsets so they overlap neighboring space. Spacing runs on rem, roughly 0.5, 1, 1.5, 3, 4, 8: tight inside controls, generous around the hero (8rem vertical padding at desktop).

Breakpoint at 48rem (768px). Below it, the floating objects collapse into a two-column grid under the type (cards side by side, badge centered full-row beneath), the route arrow is hidden, the nav drops the link pills, and display sizes switch to viewport-width units (9vw, 16.5vw, 10.6vw). Above it, the sheet becomes two columns (screenshot and requirements) with a 4rem gap.

## Elevation & Depth

A hybrid. The display type carries a hard, zero-blur extruded shadow in Deep Navy: 24 em-scaled layers, each a step of 0.0042em along both axes (about 0.1em total at rest). On a fine pointer the step direction follows the cursor (the light sits at the pointer, depth falls away from it), shifting by roughly 0.003em horizontally and 0.0024em vertically. Stuck-on objects (cards, badge) carry soft, downward navy drop shadows. The sheet casts a diffuse shadow upward. On a fine pointer the headline lines and the two cards also shift by a few pixels in parallax (lines -5, 9, 16px; cards -14, 12px at full pointer travel).

### Shadow Vocabulary
- **Extrude** (`text-shadow: 24 layers of calc(n * var(--sx, 0.0042em)) calc(n * var(--sy, 0.0042em)) 0 #0f2a47`): display type only.
- **Card lift** (`0 24px 40px -12px rgb(15 42 71 / .55), 0 6px 10px rgb(15 42 71 / .25)`): frosted device cards.
- **Badge lift** (`0 20px 30px -10px rgb(15 42 71 / .6), 0 4px 8px rgb(15 42 71 / .25)`): the lime badge.
- **Sheet rise** (`0 -20px 50px rgb(15 42 71 / .25)`): the sheet's top edge.

### Named Rules
**The Display-Only Extrude Rule.** The hard extruded shadow belongs to the display headline in this world. Cards, buttons, pills and sheet content never get hard offset shadows; they get soft lift or nothing.

## Shapes

Round and soft against a hard-edged, gridded ground. Controls are full pills (99px). Cards are large-radius (1.75rem) rounded rectangles; the screenshot frame is 2rem with a 1.2rem inner image radius; the sheet's top corners sweep 2.5rem on mobile and 3.5rem at desktop. Icons, badge, and the cursor are discs. The brand plate is a speech-bubble shape (1.1rem corners with one 0.25rem corner at bottom right). Cards and badge are rotated (-11deg, +10deg) at rest. Borders are 1px translucent white on blue (45% on pills, 50% ice on cards), 1px translucent ink on the sheet, with heavier 3px rings on discs.

## Components

### Pills (nav links, Ko-fi)
- **Shape:** full pill (99px)
- **Outline:** transparent fill, 1px white border at 45%, white text 0.8rem/600, padding 0.45rem 1rem.
- **Solid variant (Ko-fi):** white border, slightly larger (0.85rem, 0.55rem 1.3rem); hover inverts to white fill with blue text.
- **Hover:** 14% white fill and full white border, 0.25s expo ease. On a fine pointer the hovered pill leans toward the cursor (magnetic pull, 28% of the offset).

### Status Tag
- Lime pill, ink 800-weight 0.72rem uppercase, 0.06em tracking, 1.5px white border. Sits next to the brand plate in the nav, stating "Experimental".

### Notice Bar
- Full-width ink strip above the nav, white 0.78rem/600 centered text stating the experimental, non-affiliation position.

### Device Cards
- Frosted (50% deep-navy fill, 14px backdrop blur), 1px 50% ice border, 1.75rem radius, 8.8rem wide (9.5rem desktop), 3:3.6 aspect. A disc at the top holds the app icon or a stroked phone glyph, then title, subtitle, underlined hint.
- Rest: rotated, with an idle GSAP bob (14px, 3.2s) and pointer parallax. Hover, focus-visible, and selected: straighten and scale 1.04 over 0.6s expo.
- Selected (aria-pressed): lime fill, ink text and ink border; disc goes white with ink border.

### Primary Action Badge
- Lime disc (7 to 9rem), 3px 8% ink ring, rotated 10deg, with a continuous 12s spinning ring of ink uppercase 900-weight text around a stroked ink download glyph. Hover or focus scales to 1.07 and magnetically pulls toward the cursor. Spin stops under reduced motion.

### Route Tabs and Panel
- Outline pills (55% white border, 0.85rem/700) acting as a tablist; selected becomes lime with ink text. Tabs magnetically pull on hover. Panel is centered 1rem/500 text, balanced wrap, reserving 4.5em height. Tabs and cards share selection state. Content fades out 0.12s, swaps, fades in 0.45s.

### Sheet
- Near-white (#f9fafb) rounded-top surface with ink text, holding the app screenshot figure (ink frame, rounded image, caption in 85% white) beside a "Before you install" requirements definition list (6.5rem term column, 1px 14% ink dividers) and a fine print row with an ink 12% top rule.

### Cursor
- A 2.6rem lime ring (2px) trails the pointer (lerp 0.16) with a 0.5rem lime dot locked to it. The ring grows to 1.6x over links and tabs with a 92% lime fill, to 2.2x with the label "GET" over the badge, and shrinks to 0.7x on press. Over the sheet both turn blue (#1e40af), with a blue fill and white label on links. The native cursor stays. Hidden entirely on touch (hover: none, pointer: coarse) and under prefers-reduced-motion.

### Drawn Arrow
- One lime route arrow (6-unit round-cap, round-join stroke, curvy open path with hand-drawn head), hidden below 48rem. Pointer-events none. Decorative.

## Do's and Don'ts

### Do:
- **Do** keep primary blue (#1e40af) as the ground and put lime (#eff35f) only on the action, selected states, status, focus, and the cursor.
- **Do** use ink (#1a1a1a) for any text on lime or white.
- **Do** set display type in Archivo 900 at 118% width, uppercase, 0.86 line-height, -0.03em tracking, with the Deep Navy (#0f2a47) extrude; lime, white, ice from top line to bottom.
- **Do** make interactive shapes pills (99px) or discs, and large-radius (1.75rem and up) for cards and sheets.
- **Do** tilt stuck-on objects at rest (about -11deg and +10deg) and straighten them on hover, focus, and selection.
- **Do** use the shared expo-out curve (cubic-bezier(0.16, 1, 0.3, 1)) for state transitions.
- **Do** drive pointer motion through the CSS `translate` property (via --tx, --ty) so it composes with rotate and scale, with one shared GSAP ticker, and switch it all off on touch and under prefers-reduced-motion (also removing spin and transitions).
- **Do** use a 3px lime focus outline with 3px offset on blue, switching to ink on the sheet.
- **Do** keep the experimental and non-affiliation statements visible (notice bar, tag, sheet fine print).

### Don't:
- **Don't** put hard offset shadows on anything but the display headline.
- **Don't** use dark gradient dev-tool backgrounds or Apple-style polish; this world is flat saturated color.
- **Don't** use lime as decoration or on large fills beyond the badge, selected card, and selected tab.
- **Don't** use sharp-cornered rectangles for controls.
- **Don't** set running text in the expanded width or in lime.
- **Don't** replace the native cursor or make the pointer layer required; it is an enhancement only.
- **Don't** invent stats, testimonials, or imagery; rasters are the repo's own app screenshot and icon (docs/images origin).

### Not canonized (defects the build carries)
- The mobile status tag drops to 0.62rem and the cursor's GET label is 0.5rem, both below a comfortable reading size.
- The uppercase, wide-tracked status tag is a status label bound to the product's "Experimental" constraint, not a pattern for kickers or eyebrows above headings on future surfaces.
- `--blue-light` (#5080ff) and `--muted` (#ecedef) are defined but unused, so they are not recorded as palette tokens. `.arrow--cross` CSS remains with no matching element. The sheet's visually-hidden heading uses an inline style.
- Card hint text at 0.72rem on a translucent blue is small and relies on the blur backdrop for contrast.

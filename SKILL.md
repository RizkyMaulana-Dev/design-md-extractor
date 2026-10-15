---
name: design-md-extractor
description: Use when extracting a design system from UI screenshots. Slices images into bands, components, and atoms; measures color, typography, spacing, radius, motion; writes a reusable DESIGN.md. Learn the style, never copy the pixels.
---

# Design MD Extractor

Trigger phrases: "slicing UI", "extract design style", "make DESIGN.md from image",
"study this website's style".

## 1. Role

You are a **Design System Analyst + Front-end Architect**.

Read UI images, slice them into parts, learn the rules behind the appearance,
and write a `DESIGN.md` another agent can use to build a NEW site with the
same style — not a copy.

Core principle: **imitate the thinking, not the pixels.**

## 2. Input

| Input | Required | Notes |
|---|---|---|
| UI image (one or more) | Yes | Full screenshot or per-section |
| Project context | No | Brand, industry, target audience |
| Target stack | No | React, Laravel, Tailwind. Default: neutral |
| Reference width | No | Default: desktop 1440px, mobile 390px |

If the image is missing or unreadable, ask again — never invent content.
Without project context, write a generic `DESIGN.md` using the `{{Brand}}` placeholder.

## 3. Originality Rules (MANDATORY)

1. **Never** copy text, brand names, logos, illustrations, or photos from the reference.
2. Treat text only as **patterns** (length, tone, sentence structure). Examples written into `DESIGN.md` are neutral and new.
3. Colors may be extracted as **inspiration palettes**, then rounded into named, role-carrying tokens (primary, accent, ...). Suggest adjustments if the user's brand differs.
4. Layout is recorded as **patterns** ("hero centered → tile carousel → card section"), never pixel coordinates.
5. Visual assets (illustrations, photos, icons) are described by **style only** ("3D soft-render pastel"), never included.
6. If asked for a 100% clone, politely decline that part and offer: "style-inspired, with its own identity."

## 4. Workflow (run in order)

### Phase A — Observe
In 5–8 lines record: page type (landing, dashboard, catalog) and purpose; mood
(friendly / corporate / playful / minimal / bold / editorial); density
(airy / moderate / dense); theme (light / dark / mixed) and dominant color;
the signature details that make the design feel unique.

### Phase B — Slice
Three levels:

1. **Band (section)** — horizontal cuts top to bottom, named by role:
   `header`, `hero`, `showcase`, `feature-grid`, `cta`, `footer`.
2. **Component** — element groups inside each band (nav, cards, carousel, form).
3. **Atom** — smallest elements (button, badge, icon, divider, text).

For each band record: order, alignment (left/center/right), column count,
focal element, and gap to the next band.

### Phase C — Measure
Method in `references/measurement.md`. All numbers are estimates marked `~`,
rounded to clean scales (4px spacing, 2px font).

### Phase D — Abstract
Turn observations into tokens and rules:

- Colors → semantic role tokens.
- Sizes → typography and spacing scales.
- Shape → radius and border scales.
- Components → structure, variants, states.
- Repeating patterns → rules ("all cards use radius-md and a 2px border").

### Phase E — Write
Fill the template in `templates/DESIGN.md` (structure in §6). Every value must
be developer-ready.

### Phase F — Verify
Run the checklist in §8 before delivering.

## 5. Measurement (summary)

Full method: `references/measurement.md`.

- **Scale**: `scale = 1440 / W` (desktop) or `390 / W` (mobile).
- **Font size**: `font-size ≈ cap-height / 0.70`; or baseline spacing ÷ line-height. Round to 12, 13, 14, 16, 18, 20, 24, 32, 40, 48, 56, 64, 72.
- **Font identity**: classify (geometric sans / grotesk / humanist / serif / mono / display), check `a`, `g`, `y`, `R`, `Q` shapes, give 3 candidates (Google Fonts first) + confidence. Max 2 families.
- **Colors**: page, surface, ink, muted, primary, accent, line. Hex + rough 70/20/10 proportion. Flag text contrast < 4.5:1.
- **Spacing**: find the base unit (4 or 8px) and record the scale. Button heights → 36/40/44/48.
- **Shape**: pill / circle radii, 1/1.5/2px borders, soft vs hard shadows.

## 6. Output Template

Use `templates/DESIGN.md`. Section order (drop irrelevant sections, add no ornaments):

```
# DESIGN.md — {{System Name}}
## 1. Visual Character          (mood, signature, density, 6–8 traits)
## 2. Design Tokens
   2.1 Color (token table, hex, role + proportion rule)
   2.2 Typography (font, role table: size/weight/line-height/spacing)
   2.3 Spacing (scale)
   2.4 Radius
   2.5 Border & Elevation
   2.6 CSS Token Block (copy-paste)
## 3. Layout
   (frame, container, grid, alignment, ordered page anatomy)
## 4. Components
   (each: structure, size, variants, hover/active/focus states)
## 5. Text Patterns & Copywriting
   (tone, heading length, paragraph length, casing, CTA pattern, neutral examples)
## 6. Ornaments & Decoration
## 7. Imagery & Illustration    (style, ratio, frame, format)
## 8. Motion                 (duration, easing, effects, reduced-motion)
## 9. Responsive              (breakpoints, per-size changes)
## 10. Accessibility
## 11. Do & Don't
## 12. Extending the System
```

Minimum per section:

- **Typography**: Display, H2, H3, Body, Small, Eyebrow/Badge with desktop **and** mobile sizes (`clamp()` if fluid).
- **Components**: nav, button (all variants), badge, card, tile/icon, input (if present), footer, plus any signature component found.
- **Text patterns**: heading structure (e.g. "verb + benefit + object"), average word counts (heading/subtitle/CTA), casing (Title Case / Sentence case / UPPERCASE), small-text roles (stat, caption, eyebrow), 3 **original** examples using `{{Brand}}`.
- **Layout**: page anatomy as an ordered band list + alignment patterns, never coordinates.

## 7. Writing Rules

1. Match the user's language (default English); keep technical terms (CSS, tokens) in English.
2. Use **tables** for tokens and **lists** for rules; avoid long paragraphs.
3. Every number carries a unit (px, em, %).
4. Mark uncertainty: `~` for estimates, `(assumption)` for guesses, `(low confidence)` for unclear fonts/colors.
5. **300 lines max per file.** If over: `DESIGN.md` (summary + tokens + layout) plus `design/components.md`, `design/content.md`, `design/motion.md`, linked from `DESIGN.md`.
6. No long implementation code — only the CSS token block and short snippets (≤ 15 lines).
7. No "looks nice" values; everything measured or declared an assumption.
8. Never name the original site, brand, or owner.

## 8. Verification Checklist

**Completeness**

- [ ] Mood and signature style recorded
- [ ] All page bands mapped
- [ ] Role palette complete (page, surface, ink, muted, primary, accent, line)
- [ ] Typography table complete (size, weight, line-height, spacing)
- [ ] Spacing and radius scales present
- [ ] Every component has structure, variants, states
- [ ] Text patterns and copywriting documented
- [ ] Ornaments, imagery, motion, responsive, a11y covered

**Originality**

- [ ] No original text/brand/assets copied
- [ ] Example text is neutral and new
- [ ] Layout is patterns, not pixel coordinates

**Quality**

- [ ] All numbers have units, `~` where estimated
- [ ] Contrast checked
- [ ] Each file ≤ 300 lines
- [ ] A developer can build a new page from this document alone

## 9. Summary to the User

After `DESIGN.md` is done, reply briefly:

1. Files created (name + line count).
2. 3–5 signature-style points captured.
3. Assumptions/uncertainties (fonts, colors, sizes) to confirm.
4. Next-step offer: build an `AGENT.md`, scaffold initial components, or adapt the palette to the user's brand.

Do not repeat `DESIGN.md` content in chat.

## 10. Edge Cases

| Problem | Action |
|---|---|
| Low resolution | Mark sizes `~` with a range |
| Partial page | Document what's visible; mark the rest "not observed" |
| Multiple images | Merge; conflicting tokens → pick the most frequent |
| Font unidentifiable | 3 candidates + low confidence |
| Text too small | Never guess content; record its role only |

## 11. Usage Prompt Template

```
Use the design-md-extractor skill.
Images: <attach screenshot(s)>
New project: <brand / industry / audience>
Stack: <optional>
Build a DESIGN.md (≤ 300 lines per file). Learn the style, layout, UI,
text, fonts, and font sizes. Do not clone the appearance.
```

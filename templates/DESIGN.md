# DESIGN.md — {{System Name}}

> Extracted from reference screenshots by the design-md-extractor skill.
> `~` marks an estimate; `(assumption)` marks a guess.

## 1. Visual Character

- Mood:
- Signature:
- Density:
- Theme (light/dark/mixed) + dominant color:
- Defining traits:
  1.
  2.
  3.
  4.
  5.
  6.

## 2. Design Tokens

### 2.1 Color

| Token | Hex | Role | Usage |
|---|---|---|---|
| `--color-page` | | Page background | |
| `--color-surface` | | Cards, panels | |
| `--color-ink` | | Primary text | |
| `--color-muted` | | Secondary text | |
| `--color-primary` | | Brand action | |
| `--color-accent` | | Highlight | |
| `--color-line` | | Borders, dividers | |

Proportion rule: (e.g. 70/20/10)
Contrast: (flag text/background pairs < 4.5:1)

### 2.2 Typography

Font: `<primary>` (fallback `system-ui`)
Classification: | Confidence:
Candidates: 1) 2) 3)

| Role | Desktop | Mobile | Weight | Line-height | Letter-spacing |
|---|---|---|---|---|---|
| Display | | | | | |
| H2 | | | | | |
| H3 | | | | | |
| Body | | | | | |
| Small | | | | | |
| Eyebrow/Badge | | | | | |

Type ratio (display : body):

### 2.3 Spacing

Base unit: | Scale:

### 2.4 Radius

| Token | Value |
|---|---|
| `--radius-sm` | |
| `--radius-md` | |
| `--radius-lg` | |
| `--radius-pill` | |

### 2.5 Border & Elevation

### 2.6 CSS Token Block

```css
:root {
  /* color */
  --color-page: ;
  /* type */
  --font-sans: ;
  /* spacing */
  /* radius */
}
```

## 3. Layout

- Frame:
- Container (max-width):
- Grid:
- Alignment:
- Page anatomy (ordered bands):
  1. `header` —
  2. `hero` —
  3. `showcase` —
  4. `feature-grid` —
  5. `cta` —
  6. `footer` —

## 4. Components

For each: structure, sizes, variants, states (hover/active/focus).

### Nav
### Button (primary / secondary / ghost + sizes)
### Badge
### Card
### Tile / Icon
### Input
### Footer
### Signature component

## 5. Text Patterns & Copywriting

- Tone:
- Heading structure (e.g. "verb + benefit + object"):
- Average words — heading: | subtitle: | CTA:
- Casing: (Title Case / Sentence case / UPPERCASE)
- Small-text roles (stat, caption, eyebrow):
- Neutral examples (use `{{Brand}}`):
  1.
  2.
  3.

## 6. Ornaments & Decoration

## 7. Imagery & Illustration

- Style:
- Ratio:
- Frame:
- Format:

## 8. Motion

- Duration:
- Easing:
- Effects:
- `prefers-reduced-motion`:

## 9. Responsive

| Breakpoint | Changes |
|---|---|
| Mobile 390 | |
| Tablet | |
| Desktop 1440 | |

## 10. Accessibility

- Contrast flags:
- Focus visible:
- Touch target ≥ 44px:

## 11. Do & Don't

| Do | Don't |
|---|---|
| | |

## 12. Extending the System

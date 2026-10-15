# Measurement Methods from Images

Every value measured from an image is an estimate. Mark it with `~` in DESIGN.md.

## 1. Scale normalization

- Image width = `W` px.
- Desktop: `scale = 1440 / W`. Mobile: `scale = 390 / W`.
- Multiply every measured size by `scale` before recording.
- If the content canvas width is unclear, assume `max-width` 1100–1200px and write it as an assumption.

## 2. Font size

- Measure **cap height** (capital letters) or x-height.
- `font-size ≈ cap-height / 0.70` (common grotesks), or `x-height / 0.50`.
- Quick alternative: `font-size ≈ baseline spacing / line-height`.
- Round to the scale: 12, 13, 14, 16, 18, 20, 24, 32, 40, 48, 56, 64, 72.
- Record the **ratio** between levels (e.g. display : body = 4 : 1).
- Line-height: baseline spacing ÷ font-size, rounded to 1.1 / 1.2 / 1.3 / 1.5 / 1.6.
- Letter-spacing: tight (`-0.02em`), normal (`0`), wide (`0.05em+`) — from visual impression.
- Weight: thin 300, normal 400, medium 500, semibold 600, bold 700 — from relative stroke thickness.

## 3. Font identification

1. Classify: geometric sans / grotesk / humanist sans / serif / mono / display.
2. Key tells: shapes of `a`, `g`, `y`, `R`, `Q`, terminals, letter width.
3. Give **3 candidates** (Google Fonts first) + confidence (high / medium / low).
4. Set one primary font + `system-ui` fallback.
5. Max 2 families; if only one is visible, write "single family".

## 4. Spacing & element sizes

- Measure gaps between bands, card padding, grid gaps, button height, icon size.
- Find the **base unit** (usually 4 or 8px) and record it as the scale.
- Button height: edge to edge, rounded to 36/40/44/48.
- Column width: record as a ratio (1/3, 1/2) or `grid-template-columns`.

## 5. Color

- Dominant colors: page background, surface, text, accent.
- Nearest hex; if unsure write `~#xxxxxx`.
- Assign roles: page, surface, ink, muted, primary, accent, line.
- Estimate rough usage proportion (e.g. 70/20/10).
- Check main text contrast vs background; flag anything < 4.5:1.

## 6. Shape

- Radius: small / medium / large / pill / circle → px values.
- Border: 1, 1.5, 2px; color; which components use it.
- Shadow: present or not, soft or hard, direction, blur, color.

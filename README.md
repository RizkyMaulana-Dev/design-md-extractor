# design-md-extractor

Turn any UI screenshot into a build-ready `DESIGN.md` — **learn the style, never copy the pixels.**

An agent skill for Claude Code, Hermes, and any SKILL.md-compatible agent.
Point it at a screenshot of a website, app, landing page, or dashboard and it
produces a design-system document another agent (or a developer) can build a
brand-new site from — same style, own identity.

## What it does

1. **Observes** — mood, density, theme, and the signature details that make the design unique.
2. **Slices** — bands → components → atoms, with alignment and layout patterns.
3. **Measures** — colors, typography, spacing, radius, borders, motion (estimates marked `~`).
4. **Abstracts** — everything into named, role-carrying design tokens.
5. **Writes** — a `DESIGN.md` with a copy-paste CSS token block, component specs,
   copy patterns, motion, responsive, and a11y notes.

Originality is enforced: no text, brands, logos, or assets are copied — only
patterns and neutral examples.

## Installation

### Claude Code

```bash
git clone https://github.com/RizkyMaulana-Dev/design-md-extractor.git
cp -r design-md-extractor ~/.claude/skills/design-md-extractor
```

### Hermes

```bash
git clone https://github.com/RizkyMaulana-Dev/design-md-extractor.git
mkdir -p ~/.hermes/skills/creative
cp -r design-md-extractor ~/.hermes/skills/creative/design-md-extractor
```

### Any SKILL.md-compatible agent

Copy the folder containing `SKILL.md` into your agent's skills directory,
then start a new session.

## Usage

Attach one or more UI screenshots and prompt:

```
Use the design-md-extractor skill.
Images: <screenshot(s)>
New project: <brand / industry / audience>
Stack: <optional>
Build a DESIGN.md (≤ 300 lines per file). Learn the style, layout, UI,
text, fonts, and font sizes. Do not clone the appearance.
```

## What you get

| File | Contents |
|---|---|
| `DESIGN.md` | Tokens, layout, page anatomy (≤ 300 lines) |
| `design/components.md` | Component structures, variants, states (if needed) |
| `design/content.md` | Copy patterns and neutral examples (if needed) |
| `design/motion.md` | Motion spec (if needed) |

## Repository layout

```
design-md-extractor/
├── SKILL.md                 # the skill (agent-facing instructions)
├── references/
│   └── measurement.md       # how to measure from pixels
└── templates/
    └── DESIGN.md            # output skeleton
```

## License

MIT

# Starry Night — a DSH skin

Impasto indigo sky, gold stars, one small sleeping village. Painted as a Van Gogh-style
post-impressionist night landscape, then tuned so interface panels stay readable on top of it.

## Contents
- `skin.json` — manifest with dark and light palettes
- `background.jpg` — 2560×1440, 1.7 MB, JPEG q90
- `logo.svg` — two-star sparkle mark, single ink colour (`currentColor`)

## Design notes
- **Primary mode is dark.** Ink-indigo surfaces (`#070b1c` base, `#0e1631` panels) over the painting,
  with star-gold `#ffd479` as the only accent. Light mode is frosted paper over the same canvas.
- `dim 0.50`, `blur 2px`: the brushwork stays legible as texture without competing with text.
  The painting's upper-left was deliberately kept calm so the sidebar sits on quiet paint.
- `panelOpacity 0.62`, `panelBlur 16`: translucent panels. Raise toward 0.9 in Settings → Skins if you
  want more separation; drop toward 0.6 to see more sky.
- Body-text contrast, measured with WCAG relative luminance:
  - dark: label-primary on bg-layer-1 = **15.95 : 1**
  - light: label-primary on bg-layer-1 = **18.23 : 1**
  - every label on bg-base / bg-layer-2 also ≥ 4.5 : 1 in both modes.
- `radius 14`, `markSize 28`, product name **Nocturne**.
- The user-message bubble is twilight violet in dark mode and lavender in light mode.
  Edit `colors.dark.specific-bubble` or `colors.light.specific-bubble` to change it.
- No audio, no video: static only.
- Depth (`elevation-*`) and `focus-ring-width` are deliberately absent: the v1 loader validates
  every value under `colors.*` as a colour, so non-colour tokens (shadow strings, pixel widths) are
  rejected outright. Panel translucency carries the depth instead.

## Install
Copy the `starry-night` folder into `~/.config/dsh/skins/` and pick it in Settings → Skins.

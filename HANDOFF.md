# Table Builder EA — Project Handoff

## What this is
A visual table builder tool for the content team and general users. Lets users build responsive tables visually and export clean HTML + CSS snippets ready to paste anywhere (including Webflow embed blocks).

## GitHub repo
https://github.com/raikocodes/table-builder-EA
Account: `raikocodes`
Branch: `main`
Local copy: `~/Desktop/table-builder-EA/`

## GitHub Pages
https://raikocodes.github.io/table-builder-EA/

## Product direction
"Webflow for tables" — visual composer for responsive tables. Clean semantic HTML output, bring your own CSS. No tool-specific classes or wrappers. Webflow users are handled via a saved CSS preset, not baked into the tool.

## Tech stack
- Pure single-file HTML/CSS/JS — no build step, no dependencies
- PWA-ready (manifest.json, sw.js, icon.svg)
- CSS presets stored in localStorage under key `tb_presets`

## Layout
3-column layout:
1. **Left** — toolbar + table editor + live preview (with breakpoint switcher)
2. **Middle** — Visual Styles panel (scrollable)
3. **Right** — HTML output + CSS output with preset system

## Current features
- Click-to-edit table cells, add/remove rows and columns
- Dark header toggle
- Aria label field
- Live preview with breakpoint switcher (Desktop/Tablet/Landscape/Portrait)
- **Visual Styles panel** — Colors, Typography, Spacing, Borders, Responsive, Mobile Labels
  - px / rem toggle (converts all size inputs)
  - Number inputs (not sliders)
  - Each section collapsible; only Colors open by default
- CSS generated live from visual controls → updates code panel + preview
- CSS preset system — save/load/delete named presets (localStorage)
- HTML + CSS copy buttons
- Clean semantic HTML output — plain `<table>` with `data-label` attributes for mobile
- Mobile responsive CSS: stacks at configurable breakpoint, `td::before` labels fully styleable

## What was done this session
- Forked from `raikoins/table-builder` → new repo `raikocodes/table-builder-EA`
- Rebranded to EA blue/beige palette (#2B5BF5 + #F5F0E8)
- Removed Standard/Comparison table type split — one clean table type
- Removed all `cmp-wrap`/`cmp-table` classes — pure semantic HTML
- Added 3-column layout (editor / styles / code)
- Built Visual Styles panel with live CSS generation
- Added px/rem toggle
- Added Mobile Labels group (transform, weight, color, spacing, opacity)
- Default CSS driven by visual controls; responsive block included by default
- Fixed mobile preview overflow (box-sizing + overflow-x: hidden in iframe)
- Fixed mobile stacked border consistency

## Known issues / next session priorities
- Styles panel scroll works but could be polished further
- Code ↔ Visual sync not yet implemented (code edits don't update visual controls)
- File-based preset save/load (.css download/upload) not yet built
- Consider adding a "Webflow" named preset seeded on first load (clean !important overrides)
- May want to reconsider the preset UI now that presets are per-user not per-type

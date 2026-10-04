# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal portfolio site hosted on GitHub Pages. It consists of a single `index.html` with all CSS inlined in a `<style>` block — no build step, no framework, no dependencies beyond a Google Fonts CDN link.

## Deployment

Pushing to `main` deploys automatically via GitHub Pages. There is no build or test command.

## Structure

- `index.html` — the entire site: HTML, CSS (in `<style>`), and a small vanilla JS scroll animation
- `_config.yml` — Jekyll config (title/description only); Jekyll processing is effectively bypassed since the site is pure HTML
- `Ori_Picture.jpg` — profile photo referenced in `index.html`

## Design system

"Topo" theme, shared by `index.html`, `thesis.html`, and `resume.html`: a dark trail-map palette (spruce-dark `#111915` ground, brown contour ink, aspen gold `#f2b441` for accents, water blue `#8dbdd6` for links and water), Public Sans for text, and Source Serif 4 italic for captions and place names. Each page defines its tokens in `:root` inside its own `<style>` block.

- Homepage hero: a generated contour map with an alpine lake and creeks; clicking it replans an A* route (lake = obstacle, creek crossings cost extra).
- Thesis and résumé headers draw a quieter contour map (`[data-contours]` + `canvas.contours`).
- Below the header, a fixed mosaic of outdoor photos (`images/web/mosaic/`, ~21 KB tiles, lazy-loaded, slow parallax) sits behind near-opaque reading panels and dims while a panel fills mid-screen. Clicking a tile opens the full photo from `images/web/outdoors/`.
- Photos open in the "morphing" viewer (`data-gallery` groups); hobby tags float a preview on hover.
- Thesis diagrams keep their color coding: water blue = FORWARD-PF and the robots, teal = MARL, amber = baseline.
- The résumé's print stylesheet keeps a light page with a spruce accent; the mosaic and contour canvas are hidden in print.
- `designs/` holds the design previews and a comparison page (`designs/index.html`).

Photos: publish web copies only, with EXIF/GPS stripped (sips keeps GPS; re-encode with ImageIO or similar).

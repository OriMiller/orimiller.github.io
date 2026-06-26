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

CSS custom properties defined in `:root` control the color palette (dark theme: `--bg`, `--surface`, `--border`, `--text`, `--text-secondary`, `--accent`). All styling lives in the `<style>` block of `index.html` — no external stylesheet.

Key layout pattern: sections use `.fade-in` class + an `IntersectionObserver` for scroll-triggered opacity/translate animations.

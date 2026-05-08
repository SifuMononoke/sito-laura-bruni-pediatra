# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static one-page website for Dott.ssa Laura Bruni, pediatrician in San Pietro in Casale (BO). No build step, no dependencies — open `index.html` directly in a browser to preview.

## Files

- `index.html` — entire page structure and content
- `style.css` — all styles, including responsive breakpoints
- `profilepic.jpg` — doctor's profile photo
- `qrcode.png` — QR code for the MioDottore profile

## Architecture

Single HTML file with six sections (in order): sticky navbar, hero, chi-sono, orari, contatti, footer. All CSS lives in `style.css` using custom properties defined in `:root`.

**Navbar:** CSS-only hamburger menu using a hidden `<input type="checkbox" id="nav-toggle">`. The label (`.hamburger`) is its adjacent sibling; `.nav-links` is a general sibling. Selectors `#nav-toggle:checked + .hamburger` and `#nav-toggle:checked ~ .nav-links` drive the open/close state. A small inline `<script>` at the bottom of `<body>` closes the menu when a nav link is clicked.

**Responsive:** two breakpoints — `768px` (tablet, collapses grids to single column, shows hamburger) and `480px` (mobile, stacks hero buttons).

**Icons:** inline SVGs throughout, no icon font or external library.

## Key content to keep in sync

- MioDottore profile URL: `https://www.miodottore.it/laura-bruni-2` (used in navbar, hero button, and contatti card)
- Phone: `+39 351 962 5898` (used in `tel:` link, `wa.me` link, and display text)
- Email: `laurabruni@pediatra.me`
- P.IVA: `04242041201` (footer)

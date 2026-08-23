# ContrastLab

> Check a text/background color pair against WCAG 2.1 contrast thresholds, and get a passing color when it fails.

**[Live demo](https://contrastlab-mlx.vercel.app)**

Most contrast checkers tell you a pair fails and leave you to guess the fix. ContrastLab computes the ratio using the WCAG relative-luminance formula — sRGB channels linearized, weighted 0.2126/0.7152/0.0722 — and when the pair falls below 4.5:1 it proposes a replacement foreground. The suggestion converts your color to HSL and binary-searches lightness while holding hue and saturation fixed, so the fix stays recognizably your color rather than collapsing to black or white.

## Features

- Pass/fail badges for all four WCAG 2.1 thresholds: AA Normal (4.5:1), AA Large (3.0:1), AAA Normal (7.0:1), AAA Large (4.5:1)
- Ratio readout color-coded green/amber/red against the 4.5 and 3.0 boundaries
- Native color pickers plus synced hex and RGB text fields, with 3-digit shorthand hex accepted
- One-click swap of foreground and background
- Live preview rendering the pair at large (24px bold), normal (16px), and small (12px) sizes
- Suggested passing foreground with a swatch and an Apply button, shown only when the pair fails AA Normal

## Stack

- Vanilla JavaScript — a single `index.html` with no framework or runtime dependencies
- Vite as the dev server and build tool
- Contrast math, hex/RGB/HSL conversion, and the suggestion search are all hand-implemented

## Running locally

```bash
npm install
npm run dev
```

---

Part of a series of 91 small web apps. [Browse them all](https://lorenzoylosada.vercel.app).

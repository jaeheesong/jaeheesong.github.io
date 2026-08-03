# Swapping the fonts

Each option is two edits: replace the `<link href="https://fonts.googleapis.com/...">`
line in `_layouts/default.html`, and replace the three `--display` / `--body` /
`--mono` lines near the top of `assets/css/style.css`.

---

## A. Plain and modern — Inter throughout

Neutral, no serif anywhere. The most common look on new academic sites.

**Layout link:**
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
```

**CSS variables:**
```css
--display: "Inter", -apple-system, sans-serif;
--body:    "Inter", -apple-system, sans-serif;
--mono:    "IBM Plex Mono", ui-monospace, monospace;
```

Also change `.bio h1` and `.entry-title` from `font-weight: 500` to `600` —
sans faces read lighter than serifs at the same weight.

---

## B. Journal-like — Source Serif throughout

Serif for everything. Closest to how a published paper actually looks.

**Layout link:**
```html
<link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,600;1,8..60,400&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
```

**CSS variables:**
```css
--display: "Source Serif 4", Georgia, serif;
--body:    "Source Serif 4", Georgia, serif;
--mono:    "IBM Plex Mono", ui-monospace, monospace;
```

---

## C. No web fonts at all — system stack

Loads instantly, never breaks, looks slightly different on Mac vs Windows.
Plainest option.

**Layout link:** delete the three `<link>` lines for fonts.googleapis.com and
fonts.gstatic.com entirely.

**CSS variables:**
```css
--display: Georgia, "Times New Roman", serif;
--body:    -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
--mono:    ui-monospace, "SF Mono", Menlo, Consolas, monospace;
```

---

## D. Warm serif headings, sans body — Lora + Inter

Middle ground: serif titles, sans abstracts.

**Layout link:**
```html
<link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,500;0,600;1,400&family=Inter:wght@400;500&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
```

**CSS variables:**
```css
--display: "Lora", Georgia, serif;
--body:    "Inter", -apple-system, sans-serif;
--mono:    "IBM Plex Mono", ui-monospace, monospace;
```

---

## Using any other Google font

Pick it at fonts.google.com, copy the `<link>` it gives you, and put the
family name first in `--display` or `--body`. Keep a fallback after it
(`Georgia, serif` or `-apple-system, sans-serif`) so nothing breaks while the
font loads.

## Size, not family

If the problem is scale rather than shape, these are the knobs:

| What | Where in `style.css` |
|---|---|
| Overall text size | `body { font-size: 17px }` |
| Your name | `.bio h1 { font-size: 2.4rem }` |
| Paper titles | `.entry-title { font-size: 1.14rem }` |
| Section headings | `h2 { font-size: 0.74rem }` |
| Line spacing | `body { line-height: 1.62 }` |

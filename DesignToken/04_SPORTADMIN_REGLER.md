# SportAdmin-regler (DesignToken)

## 13) SportAdmin-regler (obligatoriskt)

- Allt ska ligga i ett innehållsfält.
- Ingen extern CSS/JS.
- Ingen `<style>`, inga klasser, inga media queries.
- Ingen JavaScript.
- Inga HTML-kommentarer.
- Endast inline `style`.
- Använd `px` för stabilitet.

### Ska inte finnas i innehållsblocket
- `<!doctype html>`
- `<html>`, `<head>`, `<meta>`, `<title>`, `<body>`
- `id`-attribut ska inte användas i HTML (inte tillåtet enligt denna projektstandard)
- Inline `<svg>` ska inte användas i komponenter/placeholder-lösningar i detta projekt.
  - Skäl 1: ligger utanför denna whitelist.
  - Skäl 2: kan ge instabil preview i VS Code Live Server p.g.a. script-injection/live-reload.
  - Använd istället ren HTML/CSS-placeholder (`div` + border-radius + bakgrund).

### SVG-policy (framtida användning)
- SVG är tillåtet i projektet via extern fil: använd `<img src=\"...svg\">` som standard.
- Inline `<svg>...</svg>` används endast efter uttryckligt beslut och dubbeltest.
- Obligatoriskt test vid SVG:
  1. Test i lokal preview (Live Server).
  2. Test i målmiljö/publicering (SportAdmin).
- Om problem uppstår: fallback till PNG/WebP eller ren HTML/CSS-lösning.

### Tillåtna HTML-taggar (full lista)

```
a, abbr, acronym, address, area, article, aside, b, bdi, big, blockquote,
body, br, button, caption, center, cite, code, col, colgroup, data, datalist,
dd, del, details, dfn, dir, div, dl, dt, em, fieldset, figcaption, figure,
font, footer, form, h1, h2, h3, h4, h5, h6, head, header, hr, html, i, img,
input, ins, kbd, keygen, label, legend, li, main, map, mark, menu, menuitem,
meter, nav, ol, optgroup, option, output, p, pre, progress, q, rp, rt, ruby,
s, samp, section, select, small, span, strike, strong, sub, summary, sup,
table, tbody, td, textarea, tfoot, th, thead, time, tr, tt, u, ul, var, wbr
```

### Tillåtna HTML-attribut (full lista)

```
abbr, accept-charset, accept, accesskey, action, align, alt, autocomplete,
autosave, axis, bgcolor, border, cellpadding, cellspacing, challenge, char,
charoff, charset, checked, cite, clear, color, cols, colspan, compact,
contenteditable, coords, datetime, dir, disabled, draggable, dropzone,
enctype, for, frame, headers, height, high, href, hreflang, hspace, ismap,
keytype, label, lang, list, longdesc, low, max, maxlength, media, method,
min, multiple, name, nohref, noshade, novalidate, nowrap, open, optimum,
pattern, placeholder, prompt, pubdate, radiogroup, readonly, rel, required,
rev, reversed, rows, rowspan, rules, scope, selected, shape, size, span,
spellcheck, src, start, step, style, summary, tabindex, target, title, type,
usemap, valign, value, vspace, width, wrap
```

### Tillåtna CSS-egenskaper (full lista)

```
align-content, align-items, align-self, all, animation, animation-delay,
animation-direction, animation-duration, animation-fill-mode,
animation-iteration-count, animation-name, animation-play-state,
animation-timing-function, backface-visibility, background,
background-attachment, background-blend-mode, background-clip,
background-color, background-image, background-origin, background-position,
background-position-x, background-position-y, background-repeat,
background-repeat-x, background-repeat-y, background-size, border,
border-bottom, border-bottom-color, border-bottom-left-radius,
border-bottom-right-radius, border-bottom-style, border-bottom-width,
border-collapse, border-color, border-image, border-image-outset,
border-image-repeat, border-image-slice, border-image-source,
border-image-width, border-left, border-left-color, border-left-style,
border-left-width, border-radius, border-right, border-right-color,
border-right-style, border-right-width, border-spacing, border-style,
border-top, border-top-color, border-top-left-radius, border-top-right-radius,
border-top-style, border-top-width, border-width, bottom, box-decoration-break,
box-shadow, box-sizing, break-after, break-before, break-inside, caption-side,
caret-color, clear, clip, color, column-count, column-fill, column-gap,
column-rule, column-rule-color, column-rule-style, column-rule-width,
column-span, column-width, columns, content, counter-increment, counter-reset,
cursor, direction, display, empty-cells, filter, flex, flex-basis,
flex-direction, flex-flow, flex-grow, flex-shrink, flex-wrap, float, font,
font-family, font-feature-settings, font-kerning, font-language-override,
font-size, font-size-adjust, font-stretch, font-style, font-synthesis,
font-variant, font-variant-alternates, font-variant-caps,
font-variant-east-asian, font-variant-ligatures, font-variant-numeric,
font-variant-position, font-weight, gap, grid, grid-area, grid-auto-columns,
grid-auto-flow, grid-auto-rows, grid-column, grid-column-end, grid-column-gap,
grid-column-start, grid-gap, grid-row, grid-row-end, grid-row-gap,
grid-row-start, grid-template, grid-template-areas, grid-template-columns,
grid-template-rows, hanging-punctuation, height, hyphens, image-rendering,
isolation, justify-content, left, letter-spacing, line-break, line-height,
list-style, list-style-image, list-style-position, list-style-type, margin,
margin-bottom, margin-left, margin-right, margin-top, mask, mask-clip,
mask-composite, mask-image, mask-mode, mask-origin, mask-position,
mask-repeat, mask-size, mask-type, max-height, max-width, min-height,
min-width, mix-blend-mode, object-fit, object-position, opacity, order,
orphans, outline, outline-color, outline-offset, outline-style, outline-width,
overflow, overflow-wrap, overflow-x, overflow-y, padding, padding-bottom,
padding-left, padding-right, padding-top, page-break-after, page-break-before,
page-break-inside, perspective, perspective-origin, pointer-events, position,
quotes, resize, right, row-gap, scroll-behavior, tab-size, table-layout,
text-align, text-align-last, text-combine-upright, text-decoration,
text-decoration-color, text-decoration-line, text-decoration-skip,
text-decoration-style, text-indent, text-justify, text-orientation,
text-overflow, text-shadow, text-transform, text-underline-position, top,
transform, transform-origin, transform-style, transition, transition-delay,
transition-duration, transition-property, transition-timing-function,
unicode-bidi, user-select, vertical-align, visibility, white-space, widows,
width, word-break, word-spacing, word-wrap, writing-mode, z-index
```

---



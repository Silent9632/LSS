# Design Tokens - Ljungbyss.se / SportAdmin

Detta dokument är den aktiva standarden för alla SportAdmin-sidor i projektet.
Gamla varianter är borttagna.

---

## 1) Snabbstart (arbetsordning)

När en ny sida byggs eller uppdateras, följ denna ordning:

1. Wrapper (avsnitt 2)
2. Hero A eller Hero B (avsnitt 5)
3. Huvudkort för innehållsblock (avsnitt 4)
4. Underkort vid listor/val (avsnitt 4)
5. CTA-rad med knappstilar (avsnitt 6)
6. Länkkontroll mot avsnitt 8
7. Kvalitetskontroll mot avsnitt 9-16

Undvik egna varianter om motsvarande komponent redan finns i dokumentet.

---

## 2) Grundram (alla sidor utom Meny)

```html
<div style="margin:0;background:#f3f7fb;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;color:#1a1a1a;">
  <div style="min-height:100vh;padding:40px 20px;border-radius:12px;overflow:hidden;background:linear-gradient(145deg,#edf6fc 0%,#f4f9ff 30%,#eef6fc 60%,#f7fbff 100%);">
    <div style="max-width:895px;margin:0 auto;">
      <!-- Innehåll -->
    </div>
  </div>
</div>
```

### Layout-tokens
- `max-width`: `895px`
- `container-padding`: `40px 20px`
- `section-gap`: `18px`
- `main-card-padding`: `24px`
- `sub-card-padding`: `16px`

---

## 3) Färger

### Bas
- `primary-blue`: `#005a99`
- `accent-blue`: `#0077c8`
- `surface-bg`: `rgba(255,255,255,0.88)`
- `surface-border`: `rgba(0,90,153,0.12)`
- `surface-shadow`: `0 8px 24px rgba(12,68,117,0.08)`

### Nivåfärger (simlinjen)
- Nybörjare: `#4CAF50`
- Fortsättning: `#2196F3`
- Avancerad: `#FFC107`
- Special: `#9C27B0`

---

## 4) Typografi och kortsystem

### Typografi

```css
font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif;
```

- H1: `28px`, `700`
- H2: `22px`, `700`
- H3/H4: `16-18px`, `700`
- Brödtext: `14-15px`, `line-height: 1.6`, max `65ch`
- Meta: `12-13px`, `600`

### Huvudkort

```css
background: rgba(255,255,255,0.88);
border: 1px solid rgba(0,90,153,0.12);
border-radius: 20px;
box-shadow: 0 8px 24px rgba(12,68,117,0.08);
padding: 24px;
margin-bottom: 18px;
```

### Underkort

```css
background: #ffffff;
border: 1px solid rgba(0,90,153,0.12);
border-radius: 20px;
box-shadow: 0 8px 24px rgba(12,68,117,0.08);
padding: 16px;
```

---

## 5) Hero-varianter

Använd en variant per sida (blanda inte).

### Hero A (färgad)
För landnings-/engagemangssidor med tydlig CTA.

```css
background: linear-gradient(135deg, #0077c8 0%, #005a99 100%);
color: #fff;
border-radius: 20px;
padding: 28px;
```

### Hero B (neutral)
För rena informationssidor.

```css
background: rgba(255,255,255,0.88);
border: 1px solid rgba(0,90,153,0.12);
border-radius: 20px;
box-shadow: 0 8px 24px rgba(12,68,117,0.08);
padding: 24px;
```

---

## 6) Knappar och länkar

### Primär CTA

```css
display: inline-flex;
align-items: center;
justify-content: center;
padding: 13px 24px;
min-height: 44px;
border-radius: 6px;
font-size: 15px;
font-weight: 700;
text-decoration: none;
```

### Sekundär CTA

```css
display: inline-flex;
align-items: center;
justify-content: center;
padding: 13px 24px;
min-height: 44px;
border-radius: 6px;
font-size: 15px;
font-weight: 600;
text-decoration: none;
```

### Liten länk-knapp

```css
display: inline-flex;
align-items: center;
justify-content: center;
padding: 10px 16px;
min-height: 40px;
border-radius: 6px;
font-size: 14px;
font-weight: 600;
text-decoration: none;
```

### Vanlig textlänk (ej knapp)

```css
color: #0077c8;
font-weight: 600;
text-decoration: none;
```

---

## 6.1) FAQ-komponent (standard)

Använd samma FAQ-struktur på alla sidor med frågor/svar.

- FAQ ska ligga i ett huvudkort.
- Frågor ska vara kollapsade med `details/summary`.
- Samma visuella stil som på `Ledare.html`.

### FAQ-rubrik

```css
margin: 0 0 10px 0;
color: #005a99;
line-height: 1.3;
font-size: 22px;
```

### Frågeblock (`details`)

```css
margin: 0 0 10px 0;
```

### Frågerad (`summary`)

```css
font-size: 15px;
font-weight: 700;
color: #2f4c61;
cursor: pointer;
```

### Svarstext (`details p`)

```css
margin: 8px 0 0 0;
color: #2f4c61;
line-height: 1.6;
font-size: 14px;
```

### Rekommenderad FAQ-mall

```html
<section style="background:rgba(255,255,255,0.88);border:1px solid rgba(0,90,153,0.12);border-radius:20px;box-shadow:0 8px 24px rgba(12,68,117,0.08);padding:24px;margin-bottom:18px;">
  <h2 style="margin:0 0 10px 0;color:#005a99;line-height:1.3;font-size:22px;">Vanliga frågor</h2>
  <details style="margin:0 0 10px 0;">
    <summary style="font-size:15px;font-weight:700;color:#2f4c61;cursor:pointer;">Fråga 1</summary>
    <p style="margin:8px 0 0 0;color:#2f4c61;line-height:1.6;font-size:14px;">Svar 1</p>
  </details>
  <details style="margin:0;">
    <summary style="font-size:15px;font-weight:700;color:#2f4c61;cursor:pointer;">Fråga 2</summary>
    <p style="margin:8px 0 0 0;color:#2f4c61;line-height:1.6;font-size:14px;">Svar 2</p>
  </details>
</section>
```

---

## 7) Länkpolicy

- Om länk finns i avsnitt 8 ska den användas exakt.
- Om en länk ändras: uppdatera både sidan och avsnitt 8 i samma ändring.
- Undvik relativa länkar i SportAdmin; använd full URL.
- Lägg inte in temporära `#`-länkar i publiceringsklara sidor.

Kontaktportal-specifikt:
- Frågor om simskola -> `https://ljungbyss.web.sportadmin.se/sida/?ID=161877`
- Träna och tävla -> `https://ljungbyss.web.sportadmin.se/start/?ID=161577`

---

## 8) Nyckellänkar (aktuella)

- Boka: https://sportadmin.se/book/?F=98b32003-6ad5-4a0e-aa5d-a09facfc5dab
- Simskolan och simskolegrupper: https://www.ljungbyss.se/sida/?ID=161877
- Minisim: https://www.ljungbyss.se/sida/?ID=161878
- Baddaren: https://www.ljungbyss.se/sida/?ID=161879
- Sköldpaddan: https://www.ljungbyss.se/sida/?ID=161880
- Bläckfisken: https://www.ljungbyss.se/sida/?ID=161881
- Pingvinen: https://www.ljungbyss.se/sida/?ID=161882
- Fisken steg 1: https://www.ljungbyss.se/sida/?ID=161883
- Fisken steg 2: https://www.ljungbyss.se/sida/?ID=161884
- Hajen: https://www.ljungbyss.se/sida/?ID=161885
- Hammarhajen: https://www.ljungbyss.se/sida/?ID=161888
- Fritidskortet: https://www.ljungbyss.se/sida/?ID=580304
- Simskoleavgifter / Avgifter: https://www.ljungbyss.se/sida/?ID=161889
- Simmärke: https://www.ljungbyss.se/sida/?ID=179936
- Öva i vatten: https://www.ljungbyss.se/sida/?ID=161890
- Tider och perioder / Veckoschema: https://www.ljungbyss.se/sida/?ID=332769
- Vanligt ställda frågor: https://ljungbyss.web.sportadmin.se/sida/?ID=436599
- Kontaktportal: https://www.ljungbyss.se/start/?ID=460051
- Kontaktuppgifter: https://ljungbyss.web.sportadmin.se/sida/?ID=576221
- Bli ledare: https://ljungbyss.web.sportadmin.se/sida/?ID=576223
- Webshop: https://ljungbyss.web.sportadmin.se/sida/?ID=575279
- Ljungby SS historia: https://ljungbyss.web.sportadmin.se/sida/?ID=161875

---

## 9) Teckenkodning och språk (obligatoriskt)

- All text skrivs med korrekt svenska tecken: `å ä ö Å Ä Ö`.
- Felkodade tecken får inte förekomma.
- Filer ska sparas i UTF-8 utan BOM.
- HTML-entiteter får användas sparsamt vid behov i vissa attribut, men löpande text ska vara korrekt svensk text.

Snabbkontroll i terminal:

```powershell
rg -n "Ã|Â|â|�|ï¿½" frontend
```

Om kommandot returnerar träffar ska de rättas innan publicering.

---

## 10) Checklista före publicering

1. Samma grundwrapper används.
2. `max-width:895px` används.
3. Huvudkort följer kortsystemet.
4. Knappar följer 13x24 / 10x16 + radius 6.
5. Alla länkar matchar avsnitt 8.
6. Svenska tecken är korrekta (`åäöÅÄÖ`) och inga felkodade tecken finns.
7. Filen är sparad i UTF-8 utan BOM.
8. Inga dubbla wrappers eller brutna `div`-stängningar.
9. Hero-variant är konsekvent (A eller B, inte blandat).
10. Ingen horisontell scroll på mobil.
11. Inga förbjudna HTML-taggar i innehållsblocket.
12. Inga klasser, ingen `<style>`, ingen JS.

---

## 11) Do / Don't (för konsekvent design)

### Do
- Använd samma spacing mellan sektioner (`margin-bottom:18px`).
- Använd samma kortradie (`20px`) på huvudkort och underkort.
- Använd primär/sekundär knappstil från avsnitt 6.
- Håll textbredd till ca `65ch` i längre stycken.

### Don't
- Blanda inte flera visuella stilar på samma sida.
- Lägg inte innehåll i extra specialboxar utanför kortsystemet.
- Byt inte knappstorlek per sida om det inte är ett medvetet undantag.
- Lägg inte in gamla länkar eller temporära `#`-länkar.

---

## 12) Prioritetsordning vid konflikt

Om regler krockar gäller:

1. SportAdmin-begränsningar (avsnitt 13)
2. Tillgänglighet/läsbarhet och korrekt innehåll
3. Design tokens i detta dokument
4. Sidspecifika önskemål

---

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

## 14) Definition of Done (DoD) för varje ändring

En ändring är klar först när allt nedan är uppfyllt:

1. Sidan följer grundramen och kortsystemet.
2. CTA-storlekar följer avsnitt 6.
3. Länkar matchar avsnitt 8.
4. Inga förbjudna SportAdmin-element används.
5. Ingen horisontell scroll på mobil.
6. Svenska tecken är korrekta och filen är UTF-8 utan BOM.
7. Inga brutna `div`-stängningar eller dubbla wrappers.

---

## 15) Tillåtna avvikelser (med krav)

Avvikelse från standard är tillåten endast om:

- det finns tydligt syfte (t.ex. kampanjsida, hero med särskild ton)
- sidan fortfarande följer SportAdmin-reglerna
- avvikelsen dokumenteras kort i ändringsnotering:
  - vad som avviker
  - varför
  - vilka sidor som påverkas

Om syftet är oklart: använd standarden.

---

## 16) Sida-audit mall (snabb granskning)

Använd denna mall innan publicering:

- Sida: `PATH/FIL.html`
- Hero: `A` eller `B`
- Wrapper korrekt: `Ja/Nej`
- Knappar enligt avsnitt 6: `Ja/Nej`
- Länkar validerade mot avsnitt 8: `Ja/Nej`
- ÅÄÖ/UTF-8 kontrollerat: `Ja/Nej`
- SportAdmin-regler uppfyllda: `Ja/Nej`
- Öppen risk/notering: `...`

---

## 17) Copy- och innehållsregler (mikrostandard)

- Rubriker ska vara tydliga och korta (undvik intern jargong).
- CTA-text ska vara handlingsbar: `Läs mer`, `Boka`, `Kontakta oss`, `Utforska`.
- Undvik långa textblock utan mellanrubriker.
- Undvik blandning av tonläge på samma sida (informativ vs kampanj).
- Behåll konsekvent språk: svenska, korrekt stavning, korrekt å/ä/ö.

---

## 18) Ändringslogg för detta dokument

När denna fil uppdateras, lägg till rad här:

- `YYYY-MM-DD` - vad som ändrades, och varför (1-2 rader)

Exempel:
- `2026-02-13` - lade till DoD, avvikelseregler och audit-mall för mer konsekventa AI-ändringar.

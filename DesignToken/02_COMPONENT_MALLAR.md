# Komponentmallar (DesignToken)

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

## 6.2) E-post CTA med fallback (standard)

Anv&auml;nd denna komponent p&aring; alla sidor d&auml;r e-post &auml;r en viktig handling.

Varf&ouml;r:
- `mailto:` fungerar inte alltid f&ouml;r anv&auml;ndare som enbart k&ouml;r webmail (t.ex. Gmail/Outlook.com).
- Sidan ska alltid ge en tydlig fallback med synlig e-postadress som g&aring;r att kopiera.

Regler:
- Visa en prim&auml;r knapp: `&Ouml;ppna mailapp` (`mailto:`-l&auml;nk).
- Visa e-postadressen under knapparna i en markerbar "chip".
- Anv&auml;nd `user-select:all` p&aring; adressen s&aring; den &auml;r enkel att kopiera.
- Beh&aring;ll en sekund&auml;r knapp vid behov, t.ex. `Kontaktportal`.

Rekommenderad mall:

```html
<section style="background:rgba(255,255,255,0.88);border:1px solid rgba(0,90,153,0.12);border-radius:20px;box-shadow:0 8px 24px rgba(12,68,117,0.08);padding:24px;margin-bottom:18px;">
  <h2 style="margin:0 0 10px 0;color:#005a99;line-height:1.3;font-size:22px;">Ta nasta steg</h2>
  <p style="margin:0;color:#2f4c61;line-height:1.6;font-size:14px;max-width:65ch;">
    Kontakta oss via e-post. Om knappen inte &ouml;ppnar n&aring;gon mailapp kan du kopiera adressen under.
  </p>
  <div style="margin-top:14px;display:flex;align-items:center;gap:10px;flex-wrap:wrap;">
    <a href="mailto:info@example.se?subject=Intresse" style="display:inline-flex;align-items:center;justify-content:center;padding:13px 24px;min-height:44px;border-radius:6px;border:1px solid #005a99;text-decoration:none;font-size:15px;font-weight:700;background:#005a99;color:#fff;">&Ouml;ppna mailapp</a>
    <a href="https://www.ljungbyss.se/start/?ID=460051" style="display:inline-flex;align-items:center;justify-content:center;padding:13px 24px;min-height:44px;border-radius:6px;border:1px solid #005a99;text-decoration:none;font-size:15px;font-weight:600;background:#fff;color:#005a99;">Kontaktportal</a>
  </div>
  <p style="margin:10px 0 0 0;color:#35566d;font-size:14px;line-height:1.6;">
    E-post:
    <span style="display:inline-block;padding:4px 8px;border-radius:8px;background:#eef6ff;border:1px solid #d7e7f7;color:#005a99;font-weight:700;user-select:all;">info@example.se</span>
  </p>
</section>
```

---

## 6.3) Produktsida (premium, subtil)

Anvands pa alla produktsidor under `frontend/Hem/` for en enhetlig premiumkansla.

Regler:
- En huvudsektion (undvik separat rubrik-box ovanfor innehallet).
- Visuell ordning: tillbaka-lank -> chips (kopstalle + pris) -> 2-kolumners produktgrid.
- Ingen egen H1 i HTML-blocket pa produktsidan (SportAdmin visar sidrubriken ovanfor).
- Produktbeskrivning ligger under bilden (inte under H1 i egen box).
- Kort i produktgrid ska ha mjukare premium-stil:
  - `border-radius:16px`
  - `box-shadow:0 5px 14px rgba(0,90,153,0.08)`
- Bildyta:
  - `height:310px`
  - subtil gradientbakgrund i bilden.
- Finjusteringar:
  - yttre wrapper: `padding:24px 20px 40px 20px`
  - tillbaka-lank: `margin:0 0 10px 0`
  - produkt-caption under bild: `margin:10px 0 4px 0;color:#6f8799;font-size:11px;font-weight:500;`
  - beskrivning efter caption: `margin:8px 0 0 0`
  - variant-rader i hogerkort: `line-height:1.65`

Rekommenderad mall:

```html
<section style="background:rgba(255,255,255,0.88);border:1px solid rgba(0,90,153,0.12);border-radius:20px;box-shadow:0 6px 20px rgba(0,90,153,0.07);padding:24px;margin-bottom:18px;">
  <a href="https://ljungbyss.web.sportadmin.se/sida/?ID=575279" style="display:inline-flex;align-items:center;gap:6px;margin:0 0 10px 0;color:#005a99;text-decoration:none;font-size:13px;font-weight:700;">&larr; Tillbaka till webbshop</a>

  <div style="display:flex;flex-wrap:wrap;gap:8px;margin:0 0 16px 0;">
    <span style="display:inline-block;padding:6px 10px;border-radius:999px;border:1px solid #d7e7f7;background:#f5fbff;color:#2f4c61;font-size:12px;font-weight:700;">K&ouml;pst&auml;lle: Profilh&ouml;rnan</span>
    <span style="display:inline-block;padding:6px 10px;border-radius:999px;border:1px solid #d7e7f7;background:#f5fbff;color:#2f4c61;font-size:12px;font-weight:700;">Pris: 000 kr</span>
  </div>

  <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:18px;align-items:start;">
    <article style="background:#ffffff;border:1px solid rgba(0,90,153,0.12);border-radius:16px;box-shadow:0 5px 14px rgba(0,90,153,0.08);padding:16px;">
      <div style="width:100%;height:310px;background:linear-gradient(180deg,#f8fcff 0%,#f2f9ff 100%);border:1px solid #dde9f5;border-radius:12px;display:flex;align-items:center;justify-content:center;overflow:hidden;">
        <img src="..." alt="..." style="width:100%;height:100%;object-fit:contain;">
      </div>
      <p style="margin:10px 0 4px 0;color:#6f8799;font-size:11px;font-weight:500;letter-spacing:0.01em;">Produktnamn</p>
      <p style="margin:8px 0 0 0;color:#2f4c61;line-height:1.6;font-size:14px;">Kort produktbeskrivning.</p>
    </article>

    <article style="background:#ffffff;border:1px solid rgba(0,90,153,0.12);border-radius:16px;box-shadow:0 5px 14px rgba(0,90,153,0.08);padding:16px;">
      <!-- varianter, material, pris, karta, kopinfo -->
    </article>
  </div>
</section>
```




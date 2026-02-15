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



# Core-standard (DesignToken)

> Detta dokument innehåller kärnregler. Komponentmallar, länkar och SportAdmin-regler ligger i separata filer enligt INDEX.md.

## STOPPREGEL: UTF-8 och svenska tecken
- Spara alltid filer i UTF-8.
- Använd alltid riktiga svenska tecken: å, ä, ö, Å, Ä, Ö.
- Feltecken (`Ã¥`, `Ã¤`, `Ã¶`, `�`) är blockerande fel och ska korrigeras direkt.
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
8. Meny-synk enligt avsnitt 1.1

Undvik egna varianter om motsvarande komponent redan finns i dokumentet.

### 1.1) Obligatorisk meny-synk vid nya filer

- Nya filer i `frontend` läggs alltid till i `frontend/Meny.html` i samma ändring, utan fråga.
- Länken placeras i rätt sektion (`Kontakt`, `Simskola`, `Hem`) och följer samma format som övriga poster.
- Undantag: om användaren uttryckligen säger att sidan inte ska visas i menyn.

---

## 2) Grundram (alla sidor utom Meny)

```html
<div style="margin:0;background:#f3f7fb;font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;color:#1a1a1a;">
  <div style="min-height:100vh;padding:40px 20px;border-radius:12px;overflow:hidden;background:linear-gradient(145deg,#edf6fc 0%,#f4f9ff 30%,#eef6fc 60%,#f7fbff 100%);">
    <div style="max-width:850px;margin:0 auto;">
      <!-- Innehåll -->
    </div>
  </div>
</div>
```

### Layout-tokens
- `max-width`: `850px`
- `inlägg-small-max-width`: `597px`
- `container-padding`: `40px 20px`
- `section-gap`: `18px`
- `main-card-padding`: `24px`
- `sub-card-padding`: `16px`

### Inläggsbredder (SportAdmin)
- `small` inlägg = `max-width:597px`
- Om användaren säger "small" ska `597px` användas som maxbredd för inläggets huvudcontainer.

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


## 9) Teckenkodning och språk (obligatoriskt)

- All text skrivs med korrekt svenska tecken: `å ä ö Å Ä Ö`.
- Felkodade tecken får inte förekomma.
- Filer ska sparas i UTF-8 utan BOM.
- HTML-entiteter får användas sparsamt vid behov i vissa attribut, men löpande text ska vara korrekt svensk text.

Snabbkontroll i terminal:

```powershell
rg -n "\\xC3\\x83|\\xC3\\x82|\\xE2\\x80" frontend
```

Om kommandot returnerar träffar ska de rättas innan publicering.

---

## 10) Checklista före publicering

1. Samma grundwrapper används.
2. `max-width:850px` används.
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

----

## 17) Copy- och innehållsregler (mikrostandard)

- Rubriker ska vara tydliga och korta (undvik intern jargong).
- CTA-text ska vara handlingsbar: `Läs mer`, `Boka`, `Kontakta oss`, `Utforska`.
- Undvik långa textblock utan mellanrubriker.
- Undvik blandning av tonläge på samma sida (informativ vs kampanj).
- Behåll konsekvent språk: svenska, korrekt stavning, korrekt å/ä/ö.

---

## 18) Premium Clean-recept (global standard)

Syfte: samma premiumkänsla på alla innehållssidor utan att göra designen plottrig.

### 18.1 Kärnprinciper
- Premium = lugn hierarki, hög läsbarhet, konsekvent rytm.
- Effekter ska vara diskreta och får aldrig konkurrera med innehållet.
- En sida ska ha en tydlig visuell "ryggrad": samma kortstruktur, samma spacing, samma CTA-logik.

### 18.2 Komponentregler
- **Sektionkort:** använd samma kortram överallt (`border-radius:20px`, diskret border, mjuk skugga).
- **Skugga (premium-låg):** föredra `box-shadow: 0 6px 20px rgba(0,90,153,0.07)` för innehållskort.
- **Mellanblock/tipsrutor:** lägre visuell vikt än huvudkort (ljus bakgrund, tunn border, ingen tung skugga).
- **Filmkort:** hela filmytan ska vara klickbar (thumbnail + play-overlay + badge i samma länk).
- **Rörligt innehåll:** undvik GIF/video som standard. Om det används, håll det diskret och sekundärt.

### 18.3 CTA-hierarki (obligatorisk)
- Max 1 primär CTA per sektion (fylld blå knapp).
- Övriga CTA i samma grupp ska vara sekundära (outline/ljus bakgrund).
- Primär CTA ska motsvara sidans huvudmål (t.ex. `Boka simskola`).

### 18.4 Spacing-rytm (obligatorisk)
- Mellan huvudsektioner: konsekvent (rekommenderat `margin-bottom:24px`).
- Inre kortpadding: konsekvent (rekommenderat `padding:28px` för större innehållskort).
- Rubrikblock ska ha samma vertikala rytm på alla sektioner.

### 18.5 "Gör inte"
- Ingen tung visuell konkurrens (flera starka gradienter, många skugglager, blinkande/rörliga element).
- Ingen blandad CTA-stil där alla knappar ser primära ut.
- Ingen avvikande layoutlogik på enstaka sektioner utan tydlig anledning.

---





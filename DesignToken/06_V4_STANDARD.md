# V4-standard för Ljungby Simsällskap

Detta dokument definierar `V4` som praktisk standard för uppdaterade LSS-sidor.

Syftet är att ge ett gemensamt system för:
- bakgrund
- typografi
- kort
- färglogik
- knappar
- hero
- sektioner

`V4` ska göra sidorna:
- modernare
- tydligare
- lättare att skumma
- mer sammanhängande med övriga uppdaterade LSS-sidor

Detta dokument ska användas som arbetsmall, inte bara som inspirationsbeskrivning.

---

## 1. Kärnprincip

`V4` ska vara:
- tydlig före dekorativ
- lugn före plottrig
- modern utan att bryta mot LSS-känslan
- konsekvent från sida till sida

Användaren ska snabbt förstå:
1. var den är
2. vad sidan handlar om
3. vad som är viktigast
4. vad nästa steg är

---

## 2. När V4 ska användas

`V4` passar bäst för:
- simskola
- kontakt
- om klubben
- bli ledare
- engagemangssidor
- FAQ- och vägledningssidor

För mer administrativa sidor:
- använd lugnare hero
- använd enklare sektionsflöde
- behåll samma kortsystem, typografi och CTA-logik

---

## 3. Arbetsordning vid ny eller uppdaterad V4-sida

När en sida byggs i `V4`, använd denna ordning:

1. Grundbakgrund
2. Hero (`stark` eller `lugn`)
3. Huvudkort för första innehållsdel
4. Underkort vid behov
5. CTA-rad
6. FAQ/tabell/notis-komponenter vid behov
7. Slutkontroll mot checklistan längst ner

---

## 4. Bakgrund

Alla `V4`-sidor ska använda en ljus blåvit grund med mjuk gradient.

### Standard
- `background: linear-gradient(145deg,#edf6fc 0%,#f4f9ff 30%,#eef6fc 60%,#f7fbff 100%)`
- ljus och ren bas
- inga tunga mönster
- inga starka dekorlager som konkurrerar med innehållet

### Wrapper

Rekommenderad wrapper:

```html
<div style="margin:0;background:#f3f7fb;font-family:Arial,Helvetica,sans-serif;color:#20303b;">
  <div style="min-height:100vh;padding:42px 20px 56px 20px;background:linear-gradient(145deg,#edf6fc 0%,#f4f9ff 30%,#eef6fc 60%,#f7fbff 100%);">
    <div style="max-width:850px;margin:0 auto;">
      <!-- Innehåll -->
    </div>
  </div>
</div>
```

### Standardvärden
- ytterpadding: `42px 20px 56px 20px`
- maxbredd: `850px`

---

## 5. Färglogik

Färger får inte användas fritt. De ska ha fasta roller.

### Blå
Används för:
- huvudrubriker
- huvudinformation
- informationsstruktur
- neutrala viktiga CTA

Primära toner:
- `#005a99`
- `#0077c8`

### Orange
Används för:
- förtydliganden
- uppmärksamhet
- vägledning
- viktiga notiser

Primära toner:
- `#e67e22`
- `#f29b38`

### Grön
Används för:
- trygg start
- positiv handling
- primär CTA när fokus är att börja, boka eller höra av sig

Primära toner:
- `#2e7d32`
- `#1b5e20`

### Vit / ljus vit
Används för:
- huvudkort
- underkort
- neutrala informationsytor

### Regel
Samma färg ska betyda ungefär samma sak på alla `V4`-sidor.

---

## 6. Typografi

Typografin i `V4` bygger på samma rytm som `Story_V3/V4`.

### Bas
- `font-family: Arial, Helvetica, sans-serif`
- textfärg bas: `#20303b`

### Rubriktypsnitt
- `'Trebuchet MS', Arial, Helvetica, sans-serif`

Används för:
- H1
- H2
- större statements
- viktiga processrubriker

### Typnivåer

#### H1
- `font-size: 38px`
- `line-height: 1.04`
- `letter-spacing: -0.04em`
- `font-weight: 800`

#### H2 stor
- `font-size: 32px`
- `line-height: 1.03`
- `letter-spacing: -0.03em`
- `font-weight: 800`

#### H2 normal
- `font-size: 28px`
- `line-height: 1.1`
- `letter-spacing: -0.02em`
- `font-weight: 800`

#### H3 / sektionstitel
- `font-size: 18px`
- `font-weight: 700` eller `800`

#### Korttitel
- `font-size: 16px` till `17px`
- `font-weight: 700` eller `800`

#### Brödtext stor
- `font-size: 17px`
- `line-height: 1.78`

#### Brödtext normal
- `font-size: 15px`
- `line-height: 1.75` till `1.85`

#### Hjälptext
- `font-size: 13px` till `14px`
- lägre visuell vikt

#### Etiketter / chips
- `font-size: 11px` till `13px`
- `font-weight: 700` eller `800`
- uppercase när de fungerar som sektionsmarkörer

### Regel
Rubriker ska kännas starka.
Brödtext ska kännas luftig och lätt att läsa.

---

## 7. Kortsystem

Kortsystemet är kärnan i `V4`.

Det ska finnas tre fasta nivåer:
- huvudkort
- underkort
- notisruta

### 7.1 Huvudkort

Används för:
- större sektioner
- innehållsblock
- större sammanhållna delar

### Standard
- bakgrund: vit eller nästan vit
- border: tunn blåneutral
- rundning: `26px`
- skugga: mjuk
- padding: `24px` till `28px`

Rekommenderad stil:

```html
<section style="background:rgba(255,255,255,0.92);border:1px solid rgba(0,90,153,0.12);border-radius:26px;box-shadow:0 12px 30px rgba(12,68,117,0.07);padding:26px;margin-bottom:20px;">
  ...
</section>
```

### 7.2 Underkort

Används för:
- delinformation
- rollkort
- mindre moduler i grid

### Standard
- bakgrund: vit
- border: tunn
- rundning: `20px`
- skugga: lätt
- padding: `18px` till `20px`

Rekommenderad stil:

```html
<div style="background:#ffffff;border:1px solid rgba(0,90,153,0.12);border-radius:20px;box-shadow:0 8px 20px rgba(12,68,117,0.05);padding:20px;">
  ...
</div>
```

### 7.3 Notisruta

Används för:
- förklaringar
- trygghetsbudskap
- små viktiga förtydliganden

### Standard
- lägre visuell vikt än huvudkort
- rundning: `16px`
- padding: `12px` till `16px`
- tunn border

Rekommenderad stil:

```html
<div style="padding:14px 16px;background:#fffaf4;border:1px solid rgba(230,126,34,0.12);border-radius:16px;color:#6b7280;font-size:13px;line-height:1.65;">
  ...
</div>
```

---

## 8. Radius, border och skugga

För att `V4` ska kännas som ett system måste dessa värden återkomma konsekvent.

### Rundning
- hero / stora toppkort: `30px`
- huvudkort: `26px`
- vanliga underkort: `20px`
- notisrutor / små informationsrutor: `16px`
- mindre knappar och små länkar: `10px` till `14px`

### Border
- standard: `1px solid rgba(0,90,153,0.12)`
- accentkort kan få färgtonad border i samma styrka

### Skuggor
- stora kort: `0 12px 30px rgba(12,68,117,0.07)`
- mindre kort: `0 8px 20px rgba(12,68,117,0.05)`
- hero kan vara något starkare vid behov

### Regel
Skuggor ska vara mjuka.
De får aldrig bli tyngre än innehållet.

---

## 9. Spacing-rytm

`V4` ska ha jämn rytm.

### Standard
- mellan huvudsektioner: `20px`
- mellan rubrik och första text: `14px` till `18px`
- mellan text och CTA: `14px` till `24px`
- grid-gap i sektioner: `14px` till `18px`

### Regel
Om spacing varierar för mycket förloras `V4`-känslan snabbt.

---

## 10. Hero-standard

Det ska finnas två tillåtna hero-typer i `V4`.

### 10.1 Hero stark

För:
- landningssidor
- sidor med tydlig handling
- kampanj- eller engagemangssidor

Kännetecken:
- färgad bakgrund
- stor rubrik
- stark CTA
- eventuell bilddel

### 10.2 Hero liten

För:
- informationssidor
- kontaktsidor
- styrelse- och personalsidor
- FAQ-sidor
- tabellsidor
- administrativa sidor
- sidor där användaren redan vet varför den är där

Kännetecken:
- ljus bakgrund
- tydlig men lugn introduktion
- mindre visuell dramatik
- kompakt höjd
- rubrik + kort intro
- liten etikett eller badge
- högst en knapp, annars ingen knapp alls
- ingen stor bilddel om den inte fyller ett tydligt syfte

Rekommenderad stil:

```html
<section style="margin-bottom:20px;padding:20px 22px;background:linear-gradient(180deg,rgba(255,255,255,0.94) 0%,rgba(247,251,255,0.90) 100%);border:1px solid rgba(0,90,153,0.12);border-radius:24px;box-shadow:0 12px 30px rgba(12,68,117,0.07);">
  <div style="display:inline-block;margin-bottom:10px;padding:7px 11px;border-radius:999px;background:#eef6ff;border:1px solid #d7e7f7;font-size:11px;font-weight:800;letter-spacing:0.12em;text-transform:uppercase;color:#005a99;">Kontakt</div>
  <h1 style="margin:0;font-family:'Trebuchet MS',Arial,Helvetica,sans-serif;font-size:30px;line-height:1.08;letter-spacing:-0.03em;color:#005a99;">Styrelsen</h1>
  <p style="margin:12px 0 0 0;max-width:58ch;font-size:15px;line-height:1.75;color:#5b6775;">Kort introduktion som snabbt förklarar sidan och hjälper användaren vidare utan att toppen tar för mycket plats.</p>
  <div style="margin-top:14px;display:flex;gap:10px;flex-wrap:wrap;">
    <a href="mailto:info@ljungbyss.se" style="display:inline-flex;align-items:center;justify-content:center;padding:10px 16px;min-height:40px;border-radius:10px;border:1px solid rgba(0,90,153,0.16);background:#f7fafc;color:#005a99;text-decoration:none;font-size:14px;font-weight:700;">Kontakta oss</a>
  </div>
</section>
```

### Regel
Alla sidor ska inte ha exakt samma hero-layout.
Men de ska följa samma typografiska och visuella logik.

---

## 11. CTA-standard

`V4` ska alltid ha tydlig CTA-hierarki.

### Primär CTA
Används för sidans viktigaste handling.

Exempel:
- `Boka`
- `Öppna mailapp`
- `Jag vill höra mer`

### Standard
- fylld knapp
- stark färg
- tydlig kontrast
- större vikt än övriga knappar

### Sekundär CTA
Används för alternativ eller stödjande handlingar.

Exempel:
- `Kontaktportal`
- `Se kontaktvägar`
- `Läs mer`

### Standard
- ljus eller transparent bakgrund
- tunn border
- tydligt lägre visuell vikt

### Rekommenderade knappvärden
- större CTA: `padding: 14px 24px`
- min-höjd: `46px`
- radius: `14px`
- textstorlek: `15px`

### Regel
- max en tydlig primär CTA per sektion
- övriga handlingar ska vara sekundära

---

## 12. Etiketter och sektionsmarkörer

Små etiketter får användas för att hjälpa skumning.

Exempel:
- `Rollöversikt`
- `Så går det till`
- `Ta nästa steg`
- `Varför det här spelar roll`

### Stil
- små
- tydligt separerade från rubrik
- gärna uppercase
- hög vikt men låg storlek

### Regel
Etiketter ska hjälpa orientering, inte bli dekor för dekorens skull.

### Global huvudregel för V4
Etikett ovanför rubrik är ett valfritt verktyg för sekundär orientering, inte ett standardelement som ska finnas överallt.

Det betyder:
- om rubriken redan är tydlig ska etiketten bort
- om etiketten bara upprepar rubriken med andra ord ska den bort
- om etiketten tillför ny orientering som hjälper användaren förstå var den är eller vad sektionen gör kan den användas

### När etikett är rätt
Använd etikett när minst ett av dessa villkor är uppfyllt:
- sektionen behöver visa överordnad kontext som rubriken inte själv bör bära
- sektionen byter funktion, till exempel `Ta nästa steg`, `Vanliga frågor` eller `Läs vidare`
- innehållet är långt, tätt eller delvis dolt och behöver extra skumhjälp
- etiketten hjälper användaren fatta ett snabbare val mellan olika typer av innehåll

### När etikett ska bort
Använd inte etikett när:
- H1 eller H2 redan säger samma sak tydligt
- etiketten använder nästan samma ord som rubriken
- sidan är enkel och självklar utan extra orientering
- etiketten bara tillför visuell form men ingen faktisk nytta

### Tillämpning i V4
- hero/toppsektion: `0 eller 1` etikett
- vanliga innehållssektioner: som standard ingen etikett
- hjälps- och processsektioner: etikett tillåten när den hjälper orientering
- relaterade sidor-footer: fast etikettmönster är tillåtet som del av komponenten

### Exempel
Bra:
- `Läs vidare` ovanför footer med relaterade länkar
- `Vanliga frågor` ovanför FAQ-sektion
- `Ta nästa steg` ovanför handlingssektion

Onödigt:
- `Föreningsfakta` ovanför `Grunduppgifter`
- `Kontakt och adress` ovanför `Hitta rätt väg in`
- `Förening och kontakt` ovanför `Om klubben`

---

## 13. Färgroller i sektioner

När en sida behöver flera signalnivåer ska följande logik användas:

- blå sektioner = huvudstruktur / neutral huvudinformation
- orange sektioner = förtydliganden / viktiga markeringar
- gröna sektioner = trygg start / första steg / positiv handling

### Exempel
- Tävlingsroller kan vara gröntonade
- Styrelseroller kan ha orange vägledningsaccent
- neutrala informationssektioner kan vara blåtonade

---

## 14. Bildkort

Bildkort är tillåtna och ofta bra i `V4`, men ska användas med syfte.

### Bra användning
- skapa förtroende
- förstärka känsla
- ge visuell paus
- visa verklig verksamhet

### Standard
- samma kortfamilj som övriga kort
- samma rundning
- samma skugglogik
- tydlig textdel under eller över bild

### Regel
Använd inte bilder bara för att fylla yta.

---

## 15. Informationshierarki

Alla `V4`-sidor ska byggas så att de går att förstå snabbt.

### Rekommenderad standardordning
1. Vad handlar sidan om?
2. Vad är viktigast?
3. Vad kan användaren göra här?
4. Hur går det till?
5. Vad är nästa steg?

### Regel
En användare ska kunna skumma sidan på 5-10 sekunder och förstå huvudsyftet.

---

## 16. Obligatoriska V4-komponenter

Följande komponenttyper ska finnas i systemet:

- `Hero stark`
- `Hero lugn`
- huvudkort
- underkort
- notisruta
- CTA-rad
- FAQ-kort
- tabellkort
- kontaktkort
- bildkort
- relaterade länkar-kort

### Relaterade länkar-kort

När `relaterade länkar-kort` används längst ner på en informationssida ska standardmönstret vara:
- tunn topplinje
- liten etikett, oftast `Läs vidare`
- kort rubrik
- en kort orienterande mening
- en rad sekundära länkknappar

Utgångspunkt:
- `frontend-V4/Kontakt/Hjalp_Till_I_Lss_Story_V4.html`

Detta mönster ska användas även på andra V4-infosidor om det inte finns ett tydligt skäl att avvika.
Länkarna i denna komponent ska vara riktiga slutlänkar, inte lokala preview-länkar.

---

## 17. Det som inte ska låsas för hårt

Det här ska inte standardiseras i exakt form:
- exakt samma hero-layout på alla sidor
- exakt samma mängd bilder
- exakt samma sektioner på varje sida
- unika visuella specialeffekter per sida

### Viktig princip
Det som ska bli standard är systemet bakom `V4`, inte kopian av en enskild sida.

---

## 18. Checklista vid framtida V4-konvertering

När en sida uppdateras till `V4`, kontrollera:

1. Har sidan rätt bakgrund?
2. Följer sidan `V4`-typografin?
3. Följer sidan kortsystemet?
4. Används blå/orange/grön konsekvent?
5. Är CTA-hierarkin tydlig?
6. Är spacing jämn?
7. Är sidan lätt att skumma?
8. Är nästa steg tydligt?
9. Känns sidan som samma sajt som övriga `V4`-sidor?

---

## 19. Slutlig princip

Om en sida känns:
- tydlig
- lugn
- modern
- sammanhållen med LSS
- lätt att skumma
- enkel att agera på

då följer den `V4` rätt.

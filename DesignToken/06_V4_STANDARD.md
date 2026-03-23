# V4-standard för Ljungby Simsällskap

Detta dokument beskriver `V4` som visuell standard för uppdaterade sidor i LSS-projektet.

Målet med `V4` är att:
- modernisera sidorna utan att tappa LSS-känslan
- göra sidorna tydligare och lättare att skumma
- skapa ett konsekvent system som fungerar sida för sida över tid

`V4` är inte en exakt kopia av en enskild sida.
`V4` är ett system för:
- bakgrund
- kort
- typografi
- färglogik
- CTA-hierarki
- hero-varianter

---

## 1. Kärnprincip

`V4` ska vara:
- tydlig före dekorativ
- varm men inte plottrig
- modern men inte främmande
- konsekvent från sida till sida

Varje sida ska snabbt hjälpa användaren att förstå:
1. var den är
2. vad sidan handlar om
3. vad som är viktigast
4. vad nästa steg är

---

## 2. Bakgrund

Alla `V4`-sidor ska använda en ljus blåvit grund med mjuk gradient.

### Standard
- ljus bas
- diskret blå ton
- lugn gradient
- ingen tung struktur eller starka bakgrundseffekter

### Syfte
- ge ett fräscht och modernt intryck
- knyta an till befintliga LSS-sidor
- inte konkurrera med innehållet

Rekommenderad riktning:
- `#edf6fc`
- `#f4f9ff`
- `#eef6fc`
- `#f7fbff`

---

## 3. Färglogik

Färger får inte användas fritt. De ska ha tydliga roller.

### Blå
Används för:
- huvudinformation
- rubriker
- informationsstruktur
- neutrala viktiga CTA

Rekommenderade toner:
- `#005a99`
- `#0077c8`

### Orange
Används för:
- förtydliganden
- viktiga markeringar
- vägledning
- obs eller mellanviktiga signaler

Rekommenderade toner:
- `#e67e22`
- `#f29b38`

### Grön
Används för:
- trygg start
- positiv handling
- primär CTA när fokus är att börja, boka eller höra av sig

Rekommenderade toner:
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

## 4. Typografi

Typografin i `V4` bygger på samma rytm som `Story_V3/V4`.

### Grundtypsnitt
- `Arial, Helvetica, sans-serif` för sidans bas

### Rubriktypsnitt
- `'Trebuchet MS', Arial, Helvetica, sans-serif`

Används för:
- H1
- stora H2
- tydliga statement-rubriker

### Rubriknivåer

#### H1
- cirka `38px`
- `font-weight: 800`
- `line-height: 1.04`
- `letter-spacing: -0.04em`

#### H2
- cirka `28px` eller `32px` beroende på sektion
- `font-weight: 800`
- tydlig luft under rubrik

#### H3 / underrubrik i sektion
- cirka `16px` till `18px`
- `font-weight: 700` till `800`

#### Brödtext
- cirka `15px`
- `line-height: 1.75` till `1.85`

#### Hjälptext / mindre text
- cirka `12px` till `14px`
- använd tydligt lägre visuell vikt

### Regel
Rubriker ska kännas starka.
Brödtext ska kännas lugn och lätt att läsa.

---

## 5. Kortsystem

Kortsystemet är kärnan i `V4`.

Det ska finnas tre huvudtyper:

### 5.1 Huvudkort
Används för:
- större sektioner
- huvudblock
- större informationsdelar

Rekommenderad stil:
- vit eller nästan vit bakgrund
- tunn blå border
- rundade hörn
- mjuk skugga
- generös padding

Rekommenderade värden:
- `border-radius: 20px` till `26px`
- `border: 1px solid rgba(0,90,153,0.12)`
- `box-shadow: 0 8px 24px rgba(12,68,117,0.08)`

### 5.2 Underkort
Används för:
- mindre informationsblock
- delval
- kort i grid

Rekommenderad stil:
- vit bakgrund
- tunn border
- lätt skugga
- något mindre padding än huvudkort

### 5.3 Notisruta
Används för:
- viktiga förtydliganden
- trygghetssignaler
- små praktiska budskap

Regel:
- lägre visuell vikt än huvudkort
- ska inte konkurrera med huvudrubriken

---

## 6. Hörn, border och skugga

För att `V4` ska kännas som ett system måste detta hållas konsekvent.

### Rundning
- större huvudkort: `24px` till `30px`
- normala sektionskort: `20px` till `26px`
- mindre notisrutor/chips: `14px` till `18px`

### Border
- tunn
- ren
- gärna blåneutral även när kortet har orange/grön accent

### Skugga
- mjuk
- aldrig tung eller dramatisk
- ska lyfta korten lite från bakgrunden, inte skapa visuell stökighet

---

## 7. Spacing-rytm

`V4` ska kännas luftig och jämn.

### Standard
- samma avstånd mellan huvudsektioner
- samma typ av luft mellan rubrik och text
- samma typ av luft mellan text och CTA
- samma inre padding i liknande kort

### Rekommendation
- sektion-gap: omkring `18px` till `20px`
- större kortpadding: omkring `24px` till `28px`
- mindre kortpadding: omkring `16px` till `20px`

### Regel
Om spacing varierar mycket från sektion till sektion förloras `V4`-känslan snabbt.

---

## 8. Hero-standard

Det ska finnas två tillåtna hero-varianter i `V4`.

### 8.1 Hero stark
För:
- landningssidor
- sidor med tydlig handling
- kampanj-/engagemangssidor

Kännetecken:
- färgad bakgrund
- stark rubrik
- tydlig CTA
- eventuellt bilddel

### 8.2 Hero lugn
För:
- informationssidor
- FAQ-sidor
- tabellsidor
- administrativa sidor

Kännetecken:
- ljus bakgrund
- mindre dramatik
- tydlig men lugn introduktion

### Regel
Alla sidor ska inte ha samma hero-layout.
Men alla heroes ska följa samma typografiska och visuella logik.

---

## 9. CTA-standard

`V4` ska ha tydlig knapphierarki.

### Primär CTA
Används för sidans viktigaste handling.

Exempel:
- `Boka`
- `Öppna mailapp`
- `Jag vill höra mer`

Stil:
- fylld knapp
- tydlig färg
- stark kontrast

### Sekundär CTA
Används för alternativa eller stödjande handlingar.

Exempel:
- `Kontaktportal`
- `Läs mer`
- `Se kontaktvägar`

Stil:
- ljus eller outline-liknande
- tydligt lägre vikt än primär CTA

### Regel
- max en tydlig primär CTA per sektion
- övriga handlingar ska vara visuellt sekundära

---

## 10. Etiketter och sektionsmarkörer

Små etiketter ovanför rubriker får användas som stöd för skumning.

Exempel:
- `Rollöversikt`
- `Så går det till`
- `Ta nästa steg`
- `Varför det här spelar roll`

### Stil
- små bokstäver eller uppercase
- tydlig men diskret färgkoppling
- låg till medelhög visuell vikt

### Regel
Etiketter ska hjälpa orientering, inte vara ren dekor.

---

## 11. Bildkort

Bildkort är tillåtna och ofta bra i `V4`, men ska användas med syfte.

### Bra användning
- skapa förtroende
- förstärka känsla
- ge visuell paus
- visa verksamheten på riktigt

### Regel
Använd inte bilder bara för att fylla yta.
Bildkort ska följa samma kortsystem som övriga komponenter.

---

## 12. Informationshierarki

Alla `V4`-sidor ska byggas så att de går att förstå snabbt.

Bra standardordning:
1. Vad handlar sidan om?
2. Vad är viktigast?
3. Vad kan användaren göra här?
4. Hur går det till?
5. Vad är nästa steg?

### Regel
En användare ska kunna skumma sidan på 5-10 sekunder och förstå huvudsyftet.

---

## 13. Komponenter som ska ingå i V4-systemet

Följande komponenter bör finnas som återanvändbara standarddelar:

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

---

## 14. Vad som inte ska låsas som hård standard

Det här ska inte standardiseras för hårt:

- exakt samma hero-layout på alla sidor
- exakt samma mängd bilder
- exakt samma sektioner på varje sida
- nya specialeffekter per sida
- nya färgtolkningar per sida

### Viktig princip
Det som ska bli standard är systemet bakom `V4`, inte kopian av en enskild sida.

---

## 15. När V4 passar bäst

`V4` passar särskilt bra för:
- simskola
- kontakt
- engagemangssidor
- bli ledare
- om klubben
- vägledande informationssidor

För mer administrativa sidor ska `V4` användas i lugnare form:
- mindre hero
- enklare struktur
- samma kort- och typografisystem

---

## 16. Checklista vid framtida V4-konvertering

När en sida uppdateras till `V4`, kontrollera:

1. Har sidan rätt bakgrund?
2. Följer sidan kortsystemet?
3. Följer sidan `V4`-typografin?
4. Används blå/orange/grön konsekvent?
5. Är CTA-hierarkin tydlig?
6. Känns sidan som samma sajt som övriga `V4`-sidor?
7. Är sidan lätt att skumma?
8. Är nästa steg tydligt?

---

## 17. Slutlig princip

Om en sida känns:
- tydlig
- lugn
- modern
- sammanhållen med LSS
- lätt att skumma
- enkel att agera på

då följer den `V4` rätt.

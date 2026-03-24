# Plan: Frontend V4 Rollout

**Generated**: 2026-03-24
**Estimated Complexity**: High

## Overview
Målet är att skapa en säker testyta i `frontend-V4` där hela nuvarande `frontend` kopieras och därefter uppdateras metodiskt till V4-designspråket. Arbetet ska ske sida för sida och block för block. Varje block valideras när det är klart, och varje hel sida granskas fyra gånger innan nästa sida påbörjas.

Planen bygger på tre principer:
- originalet i `frontend` lämnas orört under testfasen
- allt arbete sker i `frontend-V4`
- kvalitet säkras med en kombination av interna subagenter och officiella testverktyg
- copy får bara ändras minimalt när det verkligen behövs för tydlighet eller korrekthet

## Prerequisites
- Arbetsmapp ska vara `C:\Users\Tommy\- Projects\LSS`
- `frontend` ska kopieras till `frontend-V4`
- Relevanta designfiler ska läsas inför varje sidändring:
  - `DesignToken/01_CORE_STANDARD.md`
  - `DesignToken/04_SPORTADMIN_REGLER.md`
  - `DesignToken/02_COMPONENT_MALLAR.md` vid komponentarbete
  - `DesignToken/03_LINKS_AND_REFERENSER.md` vid länkverifiering
  - `DesignToken/06_V4_STANDARD.md`
  - `DesignToken/07_SPORTADMIN_BEST_PRACTICE.md`
- Testverktyg som rekommenderas:
  - Playwright
  - Lighthouse
  - axe-core eller Accessibility Insights
- Git-arbe tsflöde:
  - commit och push efter varje färdig sida

## Sprint 1: Setup och kvalitetssystem
**Goal**: Skapa testytan och låsa arbetsreglerna så att resten av arbetet blir stabilt.
**Demo/Validation**:
- `frontend-V4` finns och har samma struktur som `frontend`
- inga filer i originalmappen `frontend` har ändrats
- arbetsregler för sida/block/granskning är dokumenterade

### Task 1.1: Kopiera frontend till frontend-V4
- **Location**: `frontend/` -> `frontend-V4/`
- **Description**: Kopiera hela nuvarande frontend-strukturen till den nya testmappen och behåll alla filnamn och undermappar.
- **Dependencies**: Inga
- **Acceptance Criteria**:
  - `frontend-V4` finns
  - samma filnamn och mappar finns i båda träden
  - originalfiler i `frontend` är oförändrade
- **Validation**:
  - jämför filträd med `rg --files`
  - kontrollera `git status`

### Task 1.2: Definiera subagent-roller
- **Location**: Arbetsprocess, ingen specifik produktionsfil krävs
- **Description**: Lås fem roller för V4-arbetet.
- **Dependencies**: Task 1.1
- **Acceptance Criteria**:
  - rollerna är tydligt definierade
  - ansvar överlappar inte onödigt
- **Validation**:
  - rollerna kan användas konsekvent per sida

Roller:
- **Subagent A: Regelgranskare**
  - Jämför aktuell sida mot `DesignToken` och `V4`
- **Subagent B: Implementerare**
  - Uppdaterar ett block i taget i `frontend-V4`
- **Subagent C: Browser-testare**
  - Kör Playwright för layout, länkar och enkel mobilkontroll
- **Subagent D: Tillgänglighetsgranskare**
  - Kör axe, Lighthouse eller Accessibility Insights
- **Subagent E: Fyrastegsvaliderare**
  - Kör den fasta slutvalideringen i fyra omgångar och stoppar sidan om något känns avvikande
- **Huvudagent**
  - Håller ihop arbetet, fattar slutbeslut och godkänner sidan först när alla fyra valideringar är klara

### Task 1.3: Definiera klarstatus för block och sida
- **Location**: Arbetsprocess, refereras från denna plan
- **Description**: Sätt fasta regler för när ett block respektive en sida får anses klara.
- **Dependencies**: Task 1.2
- **Acceptance Criteria**:
  - samma definition används genom hela projektet
- **Validation**:
  - kan checkas av konsekvent på första testsidan

Block är klart när:
- innehållet är korrekt överfört
- layouten följer V4
- svenska tecken är korrekta
- inga förbjudna SportAdmin-element används
- länkar är korrekta om blocket innehåller länkar

Sida är klar när:
- alla block är klara
- sidan är granskad fyra gånger
- browser-test är godkänt
- tillgänglighetskontroll är genomförd
- sidan är committad och pushad

## Sprint 2: Pilot med 2-3 informationssidor
**Goal**: Bevisa att arbetsmodellen fungerar på enkla sidor innan större sidor tas.
**Demo/Validation**:
- minst två informationssidor i `frontend-V4` är klara enligt processen
- hero-liten, kortsystem och CTA-hierarki fungerar konsekvent

### Task 2.1: Välj pilotordning
- **Location**: `frontend-V4/Kontakt/` och `frontend-V4/simskola/`
- **Description**: Starta med tydliga informationssidor där V4 liten hero passar naturligt.
- **Dependencies**: Sprint 1 klar
- **Acceptance Criteria**:
  - pilotlistan är beslutad
- **Validation**:
  - ordningen är logisk och låg-risk

Rekommenderad startordning:
- `frontend-V4/Kontakt/Styrelsen.html`
- `frontend-V4/Kontakt/kontaktuppgifter.html`
- `frontend-V4/simskola/vanligt-stallda-fragor.html`
- `frontend-V4/simskola/avgifter.html`

### Task 2.2: Kör block-för-block-process på pilotsidor
- **Location**: vald sida i `frontend-V4`
- **Description**: Arbeta ett block i taget.
- **Dependencies**: Task 2.1
- **Acceptance Criteria**:
  - varje block valideras innan nästa påbörjas
  - inga spontana helombyggnader utan kontroll
- **Validation**:
  - blocklogg i arbetsrapport

Blockprocess:
1. Läs relevant sida och motsvarande designregler
2. Identifiera nästa block
3. Uppdatera endast det blocket
4. Kontrollera blocket mot reglerna
5. Dokumentera att blocket är klart

### Task 2.3: Kör fyrstegsgranskning per färdig sida
- **Location**: varje färdig pilotsida
- **Description**: När hela sidan är färdig körs fyra separata granskningar.
- **Dependencies**: Task 2.2
- **Acceptance Criteria**:
  - alla fyra granskningar är gjorda innan sidan godkänns
- **Validation**:
  - granskningsprotokoll i arbetsrapport

Fyra granskningar:
- **Granskning 1: Regelgranskning**
  - DesignToken
  - V4-standard
  - SportAdmin-regler
- **Granskning 2: Visuell och funktionell kontroll**
  - spacing
  - CTA-hierarki
  - länkar
  - mobilkänsla
  - läsbarhet
- **Granskning 3: Tillgänglighet och teknik**
  - accessibility
  - HTML-struktur
  - encoding
  - BOM/UTF-8
- **Granskning 4: Slutkontroll**
  - svenska tecken
  - konstiga formuleringar
  - ojämn rytm
  - småfel som lätt missas

## Sprint 3: Full utrullning sida för sida
**Goal**: Konvertera resten av `frontend-V4` metodiskt efter samma modell.
**Demo/Validation**:
- varje sida följer samma arbetsflöde
- inga sidor hoppar över testkedjan

### Task 3.1: Dela in sidor i arbetsgrupper
- **Location**: `frontend-V4/`
- **Description**: Konvertera efter sidtyp i stället för helt slumpmässig ordning.
- **Dependencies**: Sprint 2 klar
- **Acceptance Criteria**:
  - alla sidor ligger i en tydlig arbetsgrupp
- **Validation**:
  - prioriteringslista finns

Rekommenderad gruppordning:
- Kontakt- och informationssidor
- FAQ- och tabellsidor
- Simskolesidor
- Engagemangs- och storiesidor
- Produktsidor/Webshop
- Menysidor och översiktssidor sist

### Task 3.2: Skapa sidmallar för återkommande V4-mönster
- **Location**: referensarbete mot `DesignToken/06_V4_STANDARD.md`
- **Description**: Återanvänd samma V4-lösningar i stället för att uppfinna nytt på varje sida.
- **Dependencies**: Sprint 2 klar
- **Acceptance Criteria**:
  - återkommande sidtyper använder samma mönster
- **Validation**:
  - jämförelse mellan liknande sidor visar konsekvens

Återkommande mönster:
- infosida med `Hero liten`
- engageringssida med `Hero stark`
- FAQ-kort
- tabellkort
- kontaktkort
- relaterade länkar-kort

### Task 3.3: Commit/push efter varje godkänd sida
- **Location**: Git-historik
- **Description**: Varje klar sida sparas separat för enkel spårning och rollback.
- **Dependencies**: Task 3.1
- **Acceptance Criteria**:
  - en commit per färdig sida eller tydligt avgränsad sidgrupp
- **Validation**:
  - git-loggen är lätt att läsa

## Sprint 4: Slutvalidering av frontend-V4
**Goal**: Säkerställa att hela testmappen håller ihop som ett system.
**Demo/Validation**:
- hela `frontend-V4` känns som en enhetlig V4-front
- inga uppenbara avvikelser mellan sidor

### Task 4.1: Systemgranskning av V4-konsistens
- **Location**: hela `frontend-V4/`
- **Description**: Jämför sidor mot varandra, inte bara mot reglerna.
- **Dependencies**: Sprint 3 klar
- **Acceptance Criteria**:
  - hero-logik, kortsystem, typografi och CTA känns konsekventa
- **Validation**:
  - stickprov och jämförelse mellan sidtyper

### Task 4.2: Meny och intern länkstruktur
- **Location**: `frontend-V4/Meny.html`
- **Description**: Anpassa meny och länkar sist när övriga sidor är stabila.
- **Dependencies**: Task 4.1
- **Acceptance Criteria**:
  - menyn pekar rätt inom testmiljön
  - inga brutna interna länkar
- **Validation**:
  - Playwright-länkgenomgång

### Task 4.3: Beslutspunkt
- **Location**: projektbeslut, ingen specifik fil
- **Description**: Avgör om `frontend-V4` är tillräckligt bra för att bli nytt huvudspår.
- **Dependencies**: Task 4.2
- **Acceptance Criteria**:
  - tydligt beslut: fortsätt, justera eller ersätt original senare
- **Validation**:
  - genomgång med användaren

## Testing Strategy
- **Per block**
  - manuell regelkontroll
  - kontroll av svenska tecken och HTML-struktur
- **Per sida**
  - fyra granskningar enligt Sprint 2
  - Playwright för verklig browser-kontroll
  - Lighthouse för best practice och prestanda där relevant
  - axe-core eller Accessibility Insights för tillgänglighet
- **Per grupp av sidor**
  - jämför visuellt mot tidigare klara sidor
- **För hela systemet**
  - intern länkgenomgång
  - menygranskning
  - konsekvensgranskning

## Recommended Subagent Workflow Per Page
1. **Regelgranskare** läser sida + relevanta designfiler och markerar krav för nästa block
2. **Implementerare** uppdaterar ett block i `frontend-V4`
3. **Regelgranskare** verifierar blocket
4. Upprepa tills sidan är klar
5. **Browser-testare** kör Playwright
6. **Tillgänglighetsgranskare** kör accessibility-kontroll
7. **Fyrastegsvaliderare** kör fyra formella kontrollomgångar
8. **Huvudagent** gör slutbeslut
9. Commit + push

## Potential Risks & Gotchas
- `DesignToken/06_V4_STANDARD.md` innehåller fortfarande äldre formuleringar på vissa ställen, till exempel komponentlistan som nämner `Hero lugn` trots att standarden nu är två hero-varianter.
- Det finns risk att `frontend-V4` börjar driva innehållsförändringar i stället för designförändringar. Lås därför principen: design först, copy bara när det behövs.
- Menylänkar kan bli fel om `frontend-V4/Meny.html` ändras för tidigt. Gör den sist.
- Mobilproblem kan missas om bara desktop kontrolleras. Browser-test måste inkludera smal viewport.
- UTF-8/BOM och svenska tecken måste kontrolleras löpande, inte bara i slutet.
- Orelaterade filer i arbetsytan får inte blandas in i commits.

## Rollback Plan
- Eftersom originalet ligger kvar i `frontend` kan varje misslyckad V4-ändring stoppas utan att huvudfronten skadas.
- Om en sida i `frontend-V4` blir fel:
  - återställ bara den sidan från motsvarande fil i `frontend`
  - gör om arbetet block för block
- Om en sidgrupp visar felaktigt mönster:
  - pausa utrullningen
  - rätta sidmallen först
  - uppdatera därefter drabbade sidor

# Plan: Merge Frontend Into Single V4 Structure

**Generated**: 2026-04-19
**Estimated Complexity**: High

## Overview
Målet är att gå från två separata frontend-spår, `frontend` och `frontend-V4`, till en enda gemensam frontendstruktur där `V4` blir standard.

Detta ska göras utan att tappa innehåll, länkar eller fungerande sidor. Bästa vägen är därför inte att direkt radera `frontend` eller `frontend-V4`, utan att arbeta i tydliga steg:

1. inventera vad som faktiskt skiljer spåren
2. bestämma vilken version som ska vinna per sida
3. flytta eller ersätta sidor in i en enda slutlig `frontend`
4. uppdatera meny, interna länkar och preview
5. verifiera allt
6. först därefter ta bort den gamla dubbla strukturen

Grundprincip:
- slutmålet är en enda mapp: `frontend`
- V4-layouten blir standard där det finns en riktig V4-sida
- originalsidan behålls tillfälligt bara när V4-version saknas eller inte är klar
- `frontend-V4` tas bort sist, inte först

## Prerequisites
- Arbetsmapp ska vara `C:\Users\Tommy\- Projects\LSS`
- Alla ändringar ska sparas i UTF-8
- Relevanta designfiler ska användas vid frontendarbete:
  - `DesignToken/INDEX.md`
  - `DesignToken/01_CORE_STANDARD.md`
  - `DesignToken/04_SPORTADMIN_REGLER.md`
  - `DesignToken/06_V4_STANDARD.md`
- Git ska användas för små, säkra steg
- Lokal preview ska kunna öppnas för manuell kontroll

## Kontrollram Under Hela Arbetet
Följande kontroller ska göras löpande, inte bara i slutet:

### Kontroll A: Före varje sidbeslut
- kontrollera vilken fil som är senast ändrad
- kontrollera om den senast ändrade filen också är innehållsmässigt bäst
- kontrollera om sidan har assets, interna länkar eller menyberoenden
- kontrollera att sidnamn och placering är rimliga i slutstrukturen

### Kontroll B: Före varje filersättning
- jämför original och V4 sida visuellt och innehållsmässigt
- kontrollera rubriker, brödtext, CTA, länkar, bilder och kontaktuppgifter
- kontrollera att ingen viktig information försvinner
- kontrollera att svenska tecken ser rätt ut

### Kontroll C: Direkt efter varje filersättning
- öppna sidan i preview
- kontrollera desktopvy
- kontrollera smal mobilbredd
- kontrollera att sidan fortfarande passar in i sektionen visuellt
- kontrollera att inga uppenbara layoutfel eller brutna bilder finns

### Kontroll D: Efter varje färdig sektion
- kontrollera alla sidor i sektionen via menyn
- kontrollera att relaterade länkar inom sektionen fungerar
- kontrollera att sektionen följer V4-logiken konsekvent
- kontrollera att inga gamla länkar till `frontend-V4` finns kvar i sektionen

### Kontroll E: Före varje menyändring
- kontrollera att sidlistan för sektionen är slutligt beslutad
- kontrollera att menytext, länk och filnamn matchar varandra
- kontrollera att inga gamla eller dolda testversioner råkar ligga kvar i menyn

### Kontroll F: Direkt efter varje menyändring
- klicktesta nya eller ändrade menylänkar
- kontrollera att länkarna öppnar rätt sida
- kontrollera att inga dubbletter finns i menyn
- kontrollera att det inte finns länkar till fel mapp eller gammal variant

### Kontroll G: Före radering av `frontend-V4`
- kontrollera att alla beslut i inventeringsfilen är genomförda
- kontrollera att meny, preview och interna länkar fungerar utan `frontend-V4`
- kontrollera att alla nödvändiga assets är flyttade
- kontrollera att repo-sökning inte visar aktiva referenser till `frontend-V4`

### Kontroll H: Stoppsituationer
Arbetet ska pausas direkt om något av detta upptäcks:
- felkodade svenska tecken
- sida som blivit sämre än originalet
- meny som pekar fel
- brutna bilder eller saknade assets
- oklarhet om vilken version som faktiskt ska vinna
- osäkerhet om en sida är färdig V4 eller bara en kopia

## Sprint 1: Inventering Och Beslutsmatris
**Goal**: Få full kontroll på vilka sidor som finns i båda spåren och vilken version som ska bli slutversion.
**Demo/Validation**:
- Det finns en tydlig lista över alla sidor i `frontend` och `frontend-V4`
- Varje sida är märkt som `behåll original`, `ersätt med V4`, eller `kräver manuell sammanslagning`

### Task 1.1: Skapa sidinventering
- **Location**: `frontend/`, `frontend-V4/`
- **Description**: Lista alla HTML-filer och gruppera dem per sektion, till exempel `Kontakt`, `simskola`, `Hem` och `Inlagg Index`.
- **Dependencies**: Inga
- **Acceptance Criteria**:
  - Alla relevanta sidor finns med
  - Endast riktiga frontendfiler räknas med
- **Validation**:
  - Jämför filträd mellan båda mapparna

### Task 1.2: Märk varje sida med beslut
- **Location**: ny inventeringsfil i repo, till exempel `docs/frontend-v4-merge-inventory.md`
- **Description**: För varje sida beslutas en status:
  - `V4 vinner`
  - `Original vinner tills vidare`
  - `Manuell merge krävs`
- **Dependencies**: Task 1.1
- **Acceptance Criteria**:
  - Alla sidor har ett tydligt beslut
  - Osäkra sidor är explicit markerade
  - Senast ändrad fil är noterad per sidpar där dubbla versioner finns
- **Validation**:
  - Stickprovskontroll av flera sidor i varje kategori
  - Kontrollera commitdatum eller filhistorik för osäkra sidpar

### Task 1.3: Definiera slutregler för mappstrukturen
- **Location**: `docs/frontend-v4-merge-inventory.md` eller separat beslutsfil
- **Description**: Lås slutprinciperna för hur den enda frontenden ska se ut.
- **Dependencies**: Task 1.2
- **Acceptance Criteria**:
  - Det är beslutat att slutspåret heter `frontend`
  - Det är beslutat hur specialfiler som `index.html`, `Meny.html`, `preview-shell` och assets ska hanteras
- **Validation**:
  - Beslut går att följa utan tolkningsutrymme

## Sprint 2: Bygg Målbild I En Enda Frontend
**Goal**: Skapa den slutliga enhetliga `frontend` utan att ännu radera reservspåret.
**Demo/Validation**:
- `frontend` innehåller de sidor som ska vara slutversioner
- `frontend-V4` finns fortfarande kvar som säkerhetskoppling under arbetet

### Task 2.1: Ersätt sidor där V4 ska vinna
- **Location**: `frontend/`
- **Description**: Kopiera in V4-versionen till motsvarande plats i `frontend` för sidor där V4 tydligt är rätt slutversion.
- **Dependencies**: Sprint 1 klar
- **Acceptance Criteria**:
  - Varje ersatt sida har samma eller bättre innehåll än tidigare
  - Filnamn och sektionstillhörighet är konsekventa
- **Validation**:
  - Jämför före/efter på varje sida
  - Kontrollera att länkar fortfarande fungerar
  - Kontrollera att senast ändrad version verkligen var rätt version att flytta
  - Kontrollera preview direkt efter varje ersatt sida

### Task 2.2: Bevara originalsidor där V4 inte är redo
- **Location**: `frontend/`
- **Description**: Sidor som ännu inte har en bra V4-version lämnas kvar i original tills de byggts om eller godkänts.
- **Dependencies**: Sprint 1 klar
- **Acceptance Criteria**:
  - Ingen sida försämras bara för att nå en snabb sammanslagning
  - Osäkra sidor byts inte ut för tidigt
- **Validation**:
  - Manuell genomgång mot inventeringsfilen
  - Kontrollera att dessa sidor markeras tydligt som kvarstående arbete och inte glöms bort

### Task 2.3: Hantera sidor som kräver manuell merge
- **Location**: `frontend/` och motsvarande sida i `frontend-V4`
- **Description**: Där båda versionerna har viktiga delar görs en manuell sammanslagning: behåll bästa innehåll från original och bästa layout från V4.
- **Dependencies**: Task 2.1 och 2.2 kan pågå parallellt för andra sidor
- **Acceptance Criteria**:
  - Resultatsidan är tydligt bättre än båda tidigare varianterna
  - Ingen viktig text, bild eller länk försvinner av misstag
- **Validation**:
  - Visuell kontroll
  - Innehållskontroll rad för rad vid känsliga sidor
  - Länk- och assetkontroll innan sidan får godkännas
  - Separat kontroll av kontaktuppgifter, datum och CTA om sådant finns på sidan

## Sprint 3: Meny, Länkar Och Stödstruktur
**Goal**: Göra den sammanslagna frontenden navigerbar och intern-konsistent.
**Demo/Validation**:
- `frontend/Meny.html` pekar rätt
- Interna länkar öppnar rätt sida i samma slutliga spår
- Preview använder rätt frontend

### Task 3.1: Bygg om `frontend/Meny.html` till slutmeny
- **Location**: `frontend/Meny.html`
- **Description**: Menyn ska nu representera den enda slutliga frontenden. Alla V4-hänvisningar till separat miljö tas bort.
- **Dependencies**: Sprint 2 huvudsakligen klar
- **Acceptance Criteria**:
  - Menyn listar bara slutliga sidor
  - Ingen länk pekar till `frontend-V4`
- **Validation**:
  - Sök efter `frontend-V4` i menyn
  - Klicktest i preview
  - Kontrollera att senaste beslutade sidor faktiskt är de som länkas in
  - Kontrollera att menyordning och sektionsindelning fortfarande är logiska

### Task 3.2: Uppdatera interna länkar i sidor
- **Location**: `frontend/**/*.html`
- **Description**: Byt alla länkar som fortfarande pekar på separat V4-spår eller gammal version, så att de pekar på den enda slutliga strukturen.
- **Dependencies**: Task 3.1
- **Acceptance Criteria**:
  - Inga sidor pekar till borttagen struktur
  - Relaterade sidlänkar fungerar
- **Validation**:
  - Sök efter `frontend-V4`
  - Sök efter gamla V4-specifika menylänkar
  - Öppna stickprov av sidor med många interna länkar
  - Kontrollera att länktexter fortfarande motsvarar rätt mål

### Task 3.3: Justera preview och rotfiler
- **Location**: `index.html`, `preview-shell/`, eventuellt `frontend/index`-relaterade filer
- **Description**: Säkerställ att lokal start och preview går mot den enda slutliga frontendstrukturen.
- **Dependencies**: Task 3.1
- **Acceptance Criteria**:
  - Det finns bara ett tydligt sätt att öppna frontenden lokalt
  - Ingen förvirring mellan gammalt och nytt spår kvarstår
- **Validation**:
  - Öppna lokal preview
  - Kontrollera startsida och menyflöde
  - Kontrollera att preview inte har hårdkodade referenser till gammal V4-mapp

## Sprint 4: Full Verifiering Före Radering
**Goal**: Bevisa att den gemensamma frontenden fungerar innan den gamla dubbla strukturen tas bort.
**Demo/Validation**:
- Kritiska sidor är testade
- Inga brutna interna länkar är kända
- Meny och huvudsidor fungerar

### Task 4.1: Kontrollera huvudsektioner
- **Location**: `frontend/Kontakt/`, `frontend/simskola/`, `frontend/Hem/`, `frontend/Inlagg Index/`
- **Description**: Testa de viktigaste sidorna per sektion.
- **Dependencies**: Sprint 3 klar
- **Acceptance Criteria**:
  - Representativa sidor i varje sektion öppnar korrekt
  - Layouten håller ihop på desktop och mobilbredd
- **Validation**:
  - Manuell preview
  - Enkel mobilbreddskontroll
  - Kontrollera minst en sida med formuliknande CTA, en informationssida och en bildtung sida per sektion när det finns

### Task 4.2: Kontrollera encoding och svenska tecken
- **Location**: hela `frontend/`
- **Description**: Sök efter felkodade tecken och korrigera innan gammal struktur tas bort.
- **Dependencies**: Task 4.1
- **Acceptance Criteria**:
  - Inga blockerande encodingfel finns kvar
- **Validation**:
  - Terminalkontroll med sökning efter feltecken
  - Manuell stickprovsläsning av sidor som nyligen flyttats från V4

### Task 4.3: Kontrollera att inga referenser till gammal struktur finns kvar
- **Location**: hela repot
- **Description**: Sök efter `frontend-V4` och andra gamla referenser.
- **Dependencies**: Task 4.2
- **Acceptance Criteria**:
  - Endast tillåtna historiska planfiler får eventuellt nämna `frontend-V4`
  - Produktionssidor och preview gör det inte
- **Validation**:
  - Global sökning i repo
  - Separat kontroll i meny, preview, rotfiler och relaterade sidlänkar

## Sprint 5: Stäng Dubbla Spåret
**Goal**: Ta bort den separata V4-strukturen när slutfrontenden är verifierad.
**Demo/Validation**:
- `frontend-V4` är borttagen
- Repo har bara en aktiv frontendstruktur kvar

### Task 5.1: Ta bort `frontend-V4`
- **Location**: `frontend-V4/`
- **Description**: Radera hela den separata V4-mappen först när Sprint 4 är godkänd.
- **Dependencies**: Sprint 4 klar
- **Acceptance Criteria**:
  - Mappen finns inte längre
  - Ingen aktiv sida eller preview pekar dit
- **Validation**:
  - Filsystemkontroll
  - Global sökning efter referenser

### Task 5.2: Ta bort eller arkivera V4-specifika hjälpfiler
- **Location**: exempelvis `frontend-v4-rollout-plan.md`, V4-specifik dokumentation om den inte längre behövs
- **Description**: Bestäm vilka dokument som ska behållas som historik och vilka som ska rensas bort.
- **Dependencies**: Task 5.1
- **Acceptance Criteria**:
  - Repo innehåller inte förvirrande dubbel dokumentation i onödan
- **Validation**:
  - Manuell genomgång av root-filer

### Task 5.3: Slutlig commit för ny enfrontendsstruktur
- **Location**: hela repot
- **Description**: Samla den sista städningen i en tydlig commit när allt är verifierat.
- **Dependencies**: Task 5.1 och 5.2
- **Acceptance Criteria**:
  - Git-historiken visar tydligt när dubbelstrukturen avvecklades
- **Validation**:
  - `git status`
  - `git log --oneline`

## Recommended Working Order For LSS
- Börja med `Kontakt` eftersom flera viktiga infosidor redan finns i V4
- Fortsätt med `simskola`
- Ta `Hem` och `Webshop` därefter
- Ta `Inlagg Index` sist om posterna är mer kampanj- eller engångsbaserade
- Uppdatera `Meny.html` nära slutet, inte i början
- Radera `frontend-V4` allra sist

## Testing Strategy
- Per sida:
  - kontrollera text, rubriker, CTA och länkar
  - kontrollera mobilbredd visuellt
  - kontrollera bilder och assets
  - kontrollera svenska tecken
  - kontrollera att rätt version verkligen användes
- Per sektion:
  - öppna 2-3 representativa sidor i preview
  - klicka igenom menylänkar för sektionen
  - kontrollera intern konsekvens mellan sidorna
- Globalt:
  - sök efter `frontend-V4`
  - sök efter encodingfel
  - kontrollera att menyn bara visar slutliga sidor
  - kontrollera att inga dubblettsidor ligger kvar under andra namn
  - kontrollera att gitdiffen stämmer med det som var tänkt att ändras

## Potential Risks & Gotchas
- Vissa sidor i `frontend-V4` verkar vara verkligt omarbetade, andra verkar mest kopierade. Om allt från V4 flyttas blint kan svagare eller ofärdiga versioner råka bli slutversion.
- `frontend/Meny.html` och `frontend-V4/Meny.html` har olika roller. Om menyn byggs om för tidigt blir det lätt brutna länkar.
- Det finns redan encoding-risker i delar av projektet. Dessa måste fångas innan sammanslagningen anses klar.
- Asset-mappar i `frontend-V4` kan innehålla filer som behövs av V4-sidor. Om bara HTML flyttas men inte tillhörande bilder bryts sidorna.
- Filnamn som skiljer sig i stil, till exempel `kontaktuppgifter.html` kontra andra namn, kan skapa förvirring om inte namnstandard bestäms tidigt.

## Rollback Plan
- Arbeta i små commits per sektion eller sidgrupp
- Radera inte `frontend-V4` förrän hela den sammanslagna `frontend` är verifierad
- Om en sektion blir fel:
  - återställ bara den sektionen i git
  - behåll övriga godkända sektioner
- Om menyn blir fel:
  - återställ endast `frontend/Meny.html`
- Om en V4-sida visar sig sämre än originalet:
  - återgå till originalversionen tillfälligt
  - planera manuell merge senare

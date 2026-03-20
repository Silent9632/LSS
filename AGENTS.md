# AGENTS.md

## Syfte
- Detta dokument styr hur AI ska arbeta i LSS-projektet.
- Designregler finns i `DesignToken/` och används via läsordningen nedan.

## Regelhierarki (obligatorisk)
1. Arbetsmapp-regeln
2. Encoding-stoppregeln
3. DesignToken-läsordning
4. Meny-synkregel
5. Kvalitetscheck före avslut

## Arbetsmapp (obligatorisk)
- Arbeta endast i `C:\Users\Tommy\- Projects\LSS`.
- Använd inte andra kloner av projektet (t.ex. `C:\Users\Tommy\LSS\LSS`).

## STOPPREGEL: Encoding (obligatorisk)
- Spara alltid filer i UTF-8.
- Använd alltid korrekta svenska tecken: å, ä, ö, Å, Ä, Ö.
- Om du ser `Ã¥`, `Ã¤`, `Ã¶` eller `�`: stoppa och korrigera innan du går vidare.

## Primary design standard
- Läs alltid `DesignToken/INDEX.md` först vid design- eller frontendarbete.
- Läs därefter endast relevanta refererade filer utifrån uppgiftens scope.

## Required file set for frontend page edits
1. `DesignToken/01_CORE_STANDARD.md`
2. `DesignToken/04_SPORTADMIN_REGLER.md`
3. `DesignToken/02_COMPONENT_MALLAR.md` (om sidan innehåller CTA/FAQ/komponentsektioner)
4. `DesignToken/03_LINKS_AND_REFERENSER.md` (om sidan innehåller länkar)

## Menu sync rule
- If a new page file is created in `frontend`, add it to `frontend/Meny.html` in the same change.
- Exception: if user explicitly says not to include it in menu.

## Arbetsflöde (obligatorisk)
1. Bekräfta att aktiv projektmapp är `C:\Users\Tommy\- Projects\LSS`.
2. Läs obligatoriska DesignToken-filer före frontendändring.
3. Implementera minsta möjliga ändring för uppgiften.
4. Verifiera resultatet (funktion + layout + länkar vid behov).
5. Rapportera exakt vad som ändrats med tydliga filvägar.

## Kommunikationsregel (obligatorisk)
- Förklara alltid var en funktion finns: sida/sektion/knapp.
- Vid tekniska ord: skriv både vanligt ord och teknikord första gången.
  Exempel: `bekräftelseruta (modal)`.

## Kvalitetscheck före avslut
- UTF-8 och svenska tecken är korrekta.
- Ny sida i `frontend` är inlagd i `frontend/Meny.html` (om inte användaren sagt nej).
- Ändringar är verifierade i relevant miljö.
- Svar innehåller vad som ändrats och var.

## Chattnamn
- Alla nya chattar ska döpas enligt formatet `<Projekt> - <ämne>`.
- För detta projekt ska formatet vara `LSS - <ämne>`.

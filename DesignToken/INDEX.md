# DesignToken - Index

Använd denna fil som startpunkt. Läs alltid `01_CORE_STANDARD.md` först och därefter relevanta tillägg.

## STOPPREGEL: Teckenkodning (obligatorisk)
- Alla filer ska sparas som **UTF-8**.
- All svensk text ska skrivas med riktiga tecken: **å, ä, ö, Å, Ä, Ö**.
- Felkodade tecken (t.ex. `Ã¥`, `Ã¤`, `Ã¶`, `�`) får inte förekomma.
- Kontrollera detta vid varje ändring innan du avslutar.

## Läsordning (obligatorisk)
1. `01_CORE_STANDARD.md`
2. `04_SPORTADMIN_REGLER.md`
3. `02_COMPONENT_MALLAR.md` (när du bygger/ändrar sektioner)
4. `03_LINKS_AND_REFERENSER.md` (när du sätter eller verifierar länkar)
5. `05_CHANGELOG.md` (vid dokumentuppdateringar)

## Filöversikt
- `01_CORE_STANDARD.md`: layout, färger, typografi, checklistor, DoD, premium-recept.
- `02_COMPONENT_MALLAR.md`: knappar/länkar, FAQ-standard, e-post-CTA-fallback.
- `03_LINKS_AND_REFERENSER.md`: länkpolicy + aktuella nyckellänkar.
- `04_SPORTADMIN_REGLER.md`: tillåtna taggar/attribut/CSS och begränsningar.
- `05_CHANGELOG.md`: ändringslogg för dokumentationen.

## Regler för struktur
- Nya regler läggs i rätt del-fil, inte i index.
- Vid ny fil i `frontend`: uppdatera `frontend/Meny.html` i samma ändring (om inte användaren uttryckligen säger nej).
- Behåll svenska tecken korrekt (UTF-8).

## Hård kontroll: arbetsmapp innan ändring
- Kontrollera alltid aktiv projektrot innan filändringar.
- Om användaren anger en specifik sökväg (t.ex. `C:\Users\Tommy\- Projects\LSS`) ska ändringar göras där, inte i en annan klon.
- Om aktiv arbetsmapp inte matchar angiven sökväg: stoppa och bekräfta/byt arbetsmapp först.

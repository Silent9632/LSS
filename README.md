# LSS Frontend (SportAdmin)

Frontend-projekt för Ljungby Simsällskap (LSS), byggt som statiska HTML-sidor anpassade för SportAdmin.

## Innehåll

Projektet innehåller:
- Simskolesidor (grupper, tider, avgifter, vanliga frågor, öva i vatten)
- Kontaktsidor (kontaktportal, kontaktuppgifter, ledare, hjälp till i LSS, styrelsen, om klubben, historia)
- Menysida för lokal navigering och snabbtest

All design följer en gemensam token-standard i `DesignToken/`.

## Mappstruktur

```text
.
├─ frontend/
│  ├─ Meny.html
│  ├─ Kontakt/
│  ├─ simskola/
│  └─ Hem/
├─ DesignToken/
│  ├─ INDEX.md
│  ├─ 01_CORE_STANDARD.md
│  ├─ 02_COMPONENT_MALLAR.md
│  ├─ 03_LINKS_AND_REFERENSER.md
│  ├─ 04_SPORTADMIN_REGLER.md
│  └─ 05_CHANGELOG.md
└─ AGENTS.md
```

## Design- och kodstandard

Startpunkt för all designdokumentation:
- `DesignToken/INDEX.md`

Viktiga regler:
- UTF-8 och korrekta svenska tecken (`å, ä, ö`)
- Inline styles (SportAdmin-anpassat)
- Ingen JavaScript i publicerat innehåll
- Nya sidor i `frontend/` ska läggas till i `frontend/Meny.html` i samma ändring (om inte annat uttryckligen beställs)

## Lokal utveckling (VS Code + Live Server)

Rekommenderat:
1. Öppna projektet i VS Code.
2. Använd tillägget **Live Server**.
3. Starta från den fil du arbetar med, eller via `frontend/Meny.html`.

Tips:
- Om sidan visar gammalt innehåll: stoppa/starta Live Server och ladda om.
- Kontrollera att du använder samma URL-variant konsekvent under test.

## Arbetsflöde

1. Läs `DesignToken/INDEX.md` och relevanta delfiler.
2. Implementera ändring i HTML.
3. Verifiera visuellt i Live Server.
4. Kontrollera länkar/UTF.
5. Uppdatera meny vid nya sidor.
6. Commit + push.

## Git

Repository: `https://github.com/Silent9632/LSS`

Exempel:
```bash
git add -A
git commit -m "Beskriv ändringen tydligt"
git push
```

## Syfte

Målet är ett enhetligt, lättskött och SportAdmin-kompatibelt frontendbibliotek för LSS, med tydlig designstandard och hög konsekvens mellan sidor.

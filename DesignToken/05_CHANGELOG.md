# Ändringslogg (DesignToken)

## 19) Ändringslogg för detta dokument

När denna fil uppdateras, lägg till rad här:

- `YYYY-MM-DD` - vad som ändrades, och varför (1-2 rader)

Exempel:
- `2026-02-13` - lade till DoD, avvikelseregler och audit-mall för mer konsekventa AI-ändringar.
- `2026-02-15` - lade till standard for e-post CTA med mailto-fallback och kopierbar e-postadress for enhetlig UX.
- `2026-02-15` - lade till Premium Clean-recept (sektionkort, CTA-hierarki, spacing-rytm, filmklickyta) för enhetlig premiumdesign på alla sidor.
- `2026-02-15` - delade upp design-token dokumentationen i `DesignToken/` med `INDEX.md` + delfiler för bättre läsbarhet och underhåll.
- `2026-02-15` - gjorde `frontend/DESIGN_TOKENS.md` till redirect/stub som pekar på `DesignToken/INDEX.md`.
- `2026-02-15` - lade till `AGENTS.md` i repo-roten med regel att läsa `DesignToken/INDEX.md` först vid designarbete.
- `2026-02-15` - lade till uttrycklig regel: undvik inline `<svg>` i projektets komponenter/placeholder (whitelist + stabilitetsproblem i Live Server preview).
- `2026-02-15` - lade till SVG-policy: extern SVG via `<img>` som standard, inline SVG endast efter explicit beslut och dubbeltest (lokalt + SportAdmin).
- `2026-02-15` - uppdaterade webshoplänkar i `frontend/Hem/Webshop.html` och la in full produktlista i `DesignToken/03_LINKS_AND_REFERENSER.md`; noterat att Craft Evolve Pants tillfälligt pekar till `ID=575513` (saknad separat länk i underlag).
- `2026-02-16` - standardiserade alla aktuella produktsidor i `frontend/Hem/` till samma premium-layout (tillbaka-lank, chips, en huvudsektion, mjukare kort) och lade till ny produktside-mall i `DesignToken/02_COMPONENT_MALLAR.md`.
- `2026-02-16` - korrigerade felaktig tillbaka-lank pa alla produktsidor och i produktside-mallen: `ID=574925` -> korrekt webshop-lank `https://ljungbyss.web.sportadmin.se/sida/?ID=575279`.
- `2026-02-16` - synkade produktsidor till senaste SportAdmin-anpassade layout: ingen egen H1 i HTML-blocket, subtil produkt-caption under bild, justerad toppspacing/back-link och luftigare variantrader; uppdaterade motsvarande regler i `DesignToken/02_COMPONENT_MALLAR.md`.












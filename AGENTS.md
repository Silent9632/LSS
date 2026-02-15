# AGENTS.md

## STOPPREGEL: Encoding (obligatorisk)
- Spara alltid filer i UTF-8.
- Använd alltid korrekta svenska tecken: å, ä, ö, Å, Ä, Ö.
- Om du ser `Ã¥`, `Ã¤`, `Ã¶` eller `�`: stoppa och korrigera innan du går vidare.

## Primary design standard
- Always read `DesignToken/INDEX.md` first for design work.
- Then read relevant referenced files from `DesignToken/` based on task scope.

## Required file set for frontend page edits
1. `DesignToken/01_CORE_STANDARD.md`
2. `DesignToken/04_SPORTADMIN_REGLER.md`
3. `DesignToken/02_COMPONENT_MALLAR.md` (if page includes CTA/FAQ/components)
4. `DesignToken/03_LINKS_AND_REFERENSER.md` (if page includes links)

## Menu sync rule
- If a new page file is created in `frontend`, add it to `frontend/Meny.html` in the same change.
- Exception: if user explicitly says not to include it in menu.

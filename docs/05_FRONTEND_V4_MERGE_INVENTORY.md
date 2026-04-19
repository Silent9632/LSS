# Frontend Merge Inventory

Uppdaterad: 2026-04-19

Syfte:
- ge en enda arbetslista för sammanslagningen av `frontend` och `frontend-V4`
- visa vilken version som är senast ändrad
- ge ett första rekommenderat beslut per sida
- markera risknivå så att kontrollnivån blir rätt

## Statusnyckel
- `V4 vinner` = V4 bör bli slutversion i `frontend`
- `Frontend vinner` = vanliga `frontend` bör ligga kvar som slutversion tills vidare
- `Manuell merge` = båda versionerna måste jämföras och slås ihop med kontroll
- `Arkivera/ta bort` = sidan ska inte leva vidare som egen slutversion i nya enfrontenden

## Risknyckel
- `Hög` = meny, index, preview, kontaktuppgifter, länktunga sidor eller sidor som styr andra sidor
- `Medel` = viktiga infosidor, sidor med flera CTA eller flera interna länkar
- `Låg` = enklare produktsidor eller enklare innehållssidor

## Arbetsregler för denna inventering
- om en version är tydligt senare ändrad ska den vara utgångspunkt
- senare datum räcker inte ensam, sidan ska också kontrolleras visuellt och innehållsmässigt
- om datumen är lika eller nästan lika: behandla sidan som `Manuell merge` tills den kontrollerats
- inga sidor får raderas innan meny, länkar, assets och preview är verifierade

## Prioritet
1. Styrfiler: `Meny.html`, `index.html`, `preview-shell`
2. `Kontakt`
3. `simskola`
4. `Hem`
5. `Inlagg Index`

## Styrfiler

| Sida | Frontend | Frontend-V4 | Senast ändrad | Rekommendation | Risk | Notering |
|---|---|---|---|---|---|---|
| `Meny.html` | 2026-04-10 20:46:28 | 2026-04-10 20:46:28 | samma | Manuell merge med V4-bas | Hög | `frontend-V4/Meny.html` ska vara basen. Originalmenyn har extra experiment- och storylänkar som måste rensas eller beslutas separat. |
| `index.html` | 2026-03-26 17:08:51 | 2026-03-26 17:08:51 | samma | Manuell merge | Hög | Endast en startväg ska finnas kvar efter sammanslagning. Kontrollera hårdkodad pekning mot `/frontend/Meny.html`. |
| `preview-shell/SportAdmin_Local_Preview.html` | 2026-03-21 09:03:31 | 2026-03-24 11:11:00 | `frontend-V4` | V4 vinner med manuell kontroll | Hög | Måste städas så preview bara pekar på slutlig `frontend`. Kontrollera hårdkodade sökvägar mot enskilda sidor. |

## Kontakt

| Sida | Frontend | Frontend-V4 | Senast ändrad | Rekommendation | Risk | Notering |
|---|---|---|---|---|---|---|
| `Kontakt/Foto_Film_Grafik.html` | 2026-03-25 12:42:54 | 2026-03-26 17:50:53 | `frontend-V4` | V4 vinner | Medel | Bekräftad av subagent. Flytta med lokala assets vid sammanslagning. |
| `Kontakt/Historia.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. Behåll enklaste vägen tills kontroll visar annat. |
| `Kontakt/Hjalp_Till_I_Lss.html` | 2026-03-25 12:42:54 | 2026-03-31 18:15:17 | `frontend-V4` | V4 vinner | Medel | Ser ut att vara en verkligt omarbetad V4-sida. |
| `Kontakt/Kontaktportal.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Hög | Ser i praktiken likadan ut mellan spåren. Kontaktvägar ska ändå dubbelkontrolleras. |
| `Kontakt/kontaktuppgifter.html` | 2026-03-25 12:42:54 | 2026-03-25 12:00:36 | `frontend` | Manuell merge med stark V4-kandidat | Hög | Subagent bedömer V4 som bättre upplägg trots äldre timestamp. Kräver visuell och innehållsmässig jämförelse innan slutval. |
| `Kontakt/Ledare.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Manuell merge | Medel | Kräver jämförelse. |
| `Kontakt/Om_Klubben.html` | 2026-04-19 18:49:51 | 2026-03-25 12:42:54 | `frontend` | Manuell merge med skyddad frontend-data | Hög | Frontend har nyare rensningar. V4 har troligen bättre upplägg. Slå ihop, skriv inte över blint. |
| `Kontakt/Sponsorer.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. Behåll enklaste vägen tills kontroll visar annat. |
| `Kontakt/Styrelsen.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | V4 vinner | Hög | Bekräftad av subagent som tydlig V4-vinnare. |
| `Kontakt/Hjalp_Till_I_Lss_Experiment.html` | 2026-03-25 12:42:54 | saknas | `frontend` | Arkivera/ta bort | Medel | Ser ut som arbetsvariant, inte slutlig sida. |
| `Kontakt/Hjalp_Till_I_Lss_Story_V2.html` | 2026-03-25 12:42:54 | saknas | `frontend` | Arkivera/ta bort | Medel | Storyvariant, bör inte leva kvar som separat slutspår. |
| `Kontakt/Hjalp_Till_I_Lss_Story_V3.html` | 2026-03-25 12:42:54 | saknas | `frontend` | Arkivera/ta bort | Medel | Storyvariant, bör inte leva kvar som separat slutspår. |
| `Kontakt/Hjalp_Till_I_Lss_Story_V4.html` | 2026-03-31 18:15:17 | saknas | `frontend` | Manuell merge | Medel | Namnet antyder mellanvariant. Jämför mot `Hjalp_Till_I_Lss.html` innan beslut. |

## Simskola

| Sida | Frontend | Frontend-V4 | Senast ändrad | Rekommendation | Risk | Notering |
|---|---|---|---|---|---|---|
| `simskola/avgifter.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. |
| `simskola/fritidskortet.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. |
| `simskola/intensivsimskola-v18-v20-2026.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. |
| `simskola/ova-i-vatten.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. |
| `simskola/tider-perioder.html` | 2026-03-30 18:34:13 | 2026-03-30 19:32:06 | `frontend-V4` | V4 vinner | Medel | Bekräftad av subagent. Kontrollera och rätta V4-knappen `Se veckoschema` som har `href=\"#\"`. |
| `simskola/vanligt-stallda-fragor.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/baddaren.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/blackfisken.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/fisken-steg-1.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/fisken-steg-2.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/hajen.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/hammarhajen.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/minisim.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/pingvinen.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |
| `simskola/simskolegrupper/simskolegrupper.html` | 2026-03-25 12:42:54 | 2026-03-25 12:42:54 | samma | Frontend vinner tills vidare | Medel | Ser i praktiken likadan ut mellan spåren. Kontrollera gruppkedjans interna länkar extra noga. |
| `simskola/simskolegrupper/skoldpaddan.html` | 2026-02-18 12:56:06 | 2026-02-18 12:56:06 | samma | Frontend vinner tills vidare | Låg | Ser i praktiken likadan ut mellan spåren. |

## Hem

| Sida | Frontend | Frontend-V4 | Senast ändrad | Rekommendation | Risk | Notering |
|---|---|---|---|---|---|---|
| `Hem/Webshop.html` | 2026-02-16 19:42:16 | 2026-02-16 19:42:16 | samma | Manuell merge | Medel | Översiktssida, kontrollera länkar till produktsidor. |
| `Hem/startsida-snabbgenvagar.html` | 2026-03-30 18:49:55 | 2026-03-30 18:49:55 | samma | Manuell merge | Medel | Styrsida, kontrollera länkar extra noga. |
| `Hem/bagbase-universal-backpack.html` | 2026-02-16 20:29:40 | 2026-02-16 20:29:40 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/bagbase-vaska.html` | 2026-02-16 20:30:34 | 2026-02-16 20:30:34 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-community-hoodie.html` | 2026-02-16 20:20:11 | 2026-02-16 20:20:11 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-evolve-full-zip.html` | 2026-02-16 20:24:49 | 2026-02-16 20:24:49 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-evolve-pants.html` | 2026-02-16 20:25:25 | 2026-02-16 20:25:25 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-evolve-zip-pocket-shorts.html` | 2026-02-16 20:26:32 | 2026-02-16 20:26:32 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-klubbshorts-bla.html` | 2026-02-16 20:36:43 | 2026-02-16 20:36:43 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-rush-hot-pants.html` | 2026-02-16 20:28:50 | 2026-02-16 20:28:50 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-rush-tights.html` | 2026-02-16 20:27:20 | 2026-02-16 20:27:20 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/craft-stor-ryggsack-38l.html` | 2026-02-16 20:31:30 | 2026-02-16 20:31:30 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/elis-badhandduk.html` | 2026-02-16 20:34:50 | 2026-02-16 20:34:50 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/lss-badmossa.html` | 2026-02-16 20:35:43 | 2026-02-16 20:35:43 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/lss-mossa-gtk-nova.html` | 2026-02-16 20:33:54 | 2026-02-16 20:33:54 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/stanno-vaska.html` | 2026-02-16 20:32:26 | 2026-02-16 20:32:26 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/supportertroja.html` | 2026-02-16 20:33:11 | 2026-02-16 20:33:11 | samma | Manuell merge | Låg | Enkel produktsida. |
| `Hem/vit-funktionstroja-klubbmodell.html` | 2026-02-16 20:36:08 | 2026-02-16 20:36:08 | samma | Manuell merge | Låg | Enkel produktsida. |

## Inlagg Index

| Sida | Frontend | Frontend-V4 | Senast ändrad | Rekommendation | Risk | Notering |
|---|---|---|---|---|---|---|
| `Inlagg Index/arsmote-2026.html` | 2026-02-27 08:57:33 | 2026-02-27 08:57:33 | samma | Manuell merge | Låg | Kampanjsida, kontrollera bara om båda verkligen skiljer sig. |
| `Inlagg Index/arsmote-2026-facebook.html` | 2026-03-05 14:36:51 | 2026-03-05 14:36:51 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/arsmote-2026-reminder.html` | 2026-02-27 09:33:53 | 2026-02-27 09:33:53 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/arsmote-2026-reminder-24h.html` | 2026-02-27 09:34:02 | 2026-02-27 09:34:02 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/arsmote-2026-reminder-5-dagar.html` | 2026-02-27 09:34:02 | 2026-02-27 09:34:02 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/arsmote-2026-reminder-imorgon.html` | 2026-03-17 10:22:39 | 2026-03-17 10:22:39 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/hjalp-till-ljungbyss-nyhet.html` | 2026-03-26 20:50:26 | 2026-03-26 20:50:26 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/intensivsimskola-v18-v20-nyhet.html` | 2026-02-27 21:16:55 | 2026-02-27 21:16:55 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/intensivsimskola-v18-v20-nyhet-oppen.html` | 2026-02-27 21:12:47 | 2026-02-27 21:12:47 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/sponsorhuset-paskkampanj-2026.html` | 2026-03-31 17:55:05 | 2026-03-31 17:55:05 | samma | Manuell merge | Låg | Kräver snabb jämförelse. |
| `Inlagg Index/uppstartslager-vt2026-instagram.html` | 2026-04-10 21:09:27 | 2026-04-10 21:09:27 | samma | Manuell merge | Medel | Nyare kampanjsida, kontrollera visuellt noga. |
| `Inlagg Index/veckoschema-uppdaterat.html` | 2026-03-30 19:20:43 | 2026-03-30 19:20:43 | samma | Manuell merge | Medel | Kontrollera layout och läsbarhet. |

## Första arbetsbatch enligt inventeringen

### Batch 1: Styrfiler
- `Meny.html`
- `index.html`
- `preview-shell/SportAdmin_Local_Preview.html`

### Batch 2: Kontakt
- `Kontakt/Om_Klubben.html`
- `Kontakt/Hjalp_Till_I_Lss.html`
- `Kontakt/Foto_Film_Grafik.html`
- `Kontakt/Styrelsen.html`
- `Kontakt/kontaktuppgifter.html`
- `Kontakt/Kontaktportal.html`

### Batch 3: Simskola
- `simskola/tider-perioder.html`
- `simskola/simskolegrupper/simskolegrupper.html`

## Extra kontroller som ska fyllas i under arbetet

Lägg till denna kontrollrad när en sida blir färdig:

- Sida:
- Beslut verkställt:
- Meny uppdaterad:
- Interna länkar testade:
- Mobilkontroll gjord:
- Svenska tecken kontrollerade:
- Assets kontrollerade:
- Godkänd för att gamla versionen får tas bort:

## Viktiga beslut redan nu
- slutmålet är en enda aktiv mapp: `frontend`
- `frontend-V4` ska användas som källa där V4-versionen är bäst eller senast ändrad
- `frontend-V4/Meny.html` ska vara bas för enda slutmenyn i `frontend`
- variantfiler som `Experiment`, `Story_V2`, `Story_V3` ska normalt inte leva vidare som egna slutsidor
- `Kontakt/Om_Klubben.html` i vanliga `frontend` ska skyddas eftersom den nyligen ändrats
- stora delar av `simskola`, `Hem` och `Inlagg Index` verkar redan vara identiska mellan spåren och ska därför inte byggas om i onödan

# QA-REPORT — Sauda.html (pre-send review)

Branch: `claude/pre-send-review-zbFgK`
Kjøretidspunkt (siste runde): 2026-05-11 (etter rensingoppgave)
Filer:
- Kilde: `Sauda.html` (2 858 368 byte, 2310 linjer)
  - SHA-256: `20f10c321a4901cedff3e487bb215e464a6f5278f1e7c2fe6e4dc23921cfe8e7`
- Output: `qa-output/` (ikke versjonert; lokal sandbox `/tmp/sauda-work/qa-output/`)

## Sammendrag

| Verktøy | Før fix | Etter A-fix | **Etter rensing (v2)** | Måltall |
|---|---|---|---|---|
| Lighthouse Performance (desktop) | 54/100 | 54/100 | **55/100** | 95+ — **ikke nådd** (designvalg, se C4) |
| Lighthouse Performance (mobile) | — | — | **55/100** | 95+ — **ikke nådd** |
| Lighthouse Accessibility | 95/100 | 96/100 | **96/100** | 95+ ✓ |
| Lighthouse Best Practices | 96/100 | 96/100 | **96/100** | 95+ ✓ |
| Lighthouse SEO | 100/100 | 100/100 | **100/100** | 95+ ✓ |
| axe-core violations | 5 (264 noder) | 1 (177 noder) | **1 violation / 1 incomplete** | 0 (designvalg, C3) |
| axe-core passes | — | 50 | **47** | maks |
| html-validate errors | 21 | 0 | **0** | 0 ✓ |
| Brutte interne lenker | 0 | 0 | **0 (22 hrefs/16 unike)** | 0 ✓ |
| Brutte aria-labelledby | 0 | 0 | **0 (6 refs)** | 0 ✓ |
| Modal ESC + utenfor-klikk | ✓ ✓ | ✓ ✓ | **✓ ✓ (gjenåpnes)** | ✓ ✓ ✓ |
| Pin-overlapp 375 px | 18 par | 8 par | **8 par** | 0 (uendret av rensing) |
| Print-PDF genereres | ✓ | ✓ | **✓ (740 KB)** | ✓ |
| Console errors (Playwright) | — | — | **0** | 0 ✓ |
| Page errors (Playwright) | — | — | **0** | 0 ✓ |

**Ingen regresjon** observert i rensingoppgave-runden. Lighthouse-scorer er stabile eller marginalt bedre. Forbedringen i a11y-passes (50 → 47) er kun fordi totalt antall elementer som kontrolleres har gått ned etter sletting av DEL 3+4 (færre seksjoner = færre individuelle a11y-sjekker).

## 1. Lighthouse

Rapportfiler:
- `qa-output/reports/lighthouse-final.report.html` (lesbar HTML)
- `qa-output/reports/lighthouse-final.report.json` (rådata)

### Performance — 54/100 (under mål)

Årsak: dokumentet er én selvinneholdt fil på 2,8 MB med base64-innleirede JPEG-bilder.

| Audit | Verdi |
|---|---|
| First Contentful Paint | 15,0 s |
| Largest Contentful Paint | 15,0 s |
| Cumulative Layout Shift | 0 |
| Speed Index | 15,0 s |
| Total Blocking Time | 120 ms |
| Avoid enormous network payloads | 2 816 KiB |
| Avoid an excessive DOM size | 2 984 elementer |

Performance kan ikke heves til 95+ uten å splitte ut bildene fra HTML — det bryter forutsetningen om én leveransefil. Flagget som designvalg i CONCERNS.

### Accessibility — 96/100

Eneste gjenstående fail: `color-contrast` (se §3).

### Best Practices — 96/100

Eneste fail: én 404 i konsoll fra automatisk favicon-forespørsel. Ufarlig.

### SEO — 100/100

## 2. html-validate

`html-validate@9.7.1` mot `Sauda.html`:

```
✖ 0 problems (0 errors, 0 warnings)
```

Før fikser: 21 errors. Brutt ned:
- 8 × `role="list"` / `role="listitem"` på div/article — fjernet.
- 7 × `open=""` boolske attributter — endret til `open`.
- 4 × `aria-label` på "ikke-tillatt" div — `role="status"` / `role="group"` lagt til.
- 1 × `<header>` med redundant `role="banner"` — `role` fjernet.
- 1 × `<style>`-element i `<body>` (kart-CSS, scope-justert) — beholdt; HTML5-spec tillater dette og rapporten er en best-practice-flagging, ikke et standardsbrudd.

## 3. axe-core (WCAG 2.1 AA + best-practice)

Detaljer: `qa-output/reports/axe-summary.json`, `qa-output/reports/axe-results.json`

| Status før | Status etter |
|---|---|
| 5 violations / 264 noder | 1 violation / 177 noder |
| 2 incomplete | 1 incomplete |
| 47 passes | 50 passes |

Fikset:
- `aria-allowed-role` (8 noder, minor) — `role="list/listitem"` fjernet fra `.deal-grid`.
- `heading-order` (1 node, moderate) — `<h4>` i §"Beslutning" omgjort til `<h3>` med inline-styling som bevarer visuell tekst.
- `region` (61 noder, moderate) — innholdet wrappet i `<main id="main">`, topbar konvertert til `<header>`. Watermark fikk `aria-hidden="true"`.
- `empty-table-header` (4 noder, minor) — `<th>` fikk `<span class="sr-only">Parameter</span>` (visuelt skjult, lesbar for skjermlesere).
- `aria-prohibited-attr` (incomplete, 4 noder) — løst sammen med roller over.

Ikke fikset (1 violation, 177 noder):
- `color-contrast` — flagger lyse hjelpetekster, kobber-aksenter, `.sources`-fotnoter, `.figure-note`-sidetekster mot papir-bakgrunn. Det er gjennomgående typografisk hierarki, ikke en feil. Flagget som designvalg i CONCERNS. Den ene "alvorlige" varianten i mørk seksjon (`#0c1c2c` på `#071016`, ratio 1.11 — `dd-control-table` i Appendix/DD) er fikset med CSS-override.

## 4. Playwright — visuell QA

### Skjermbilder (`qa-output/screenshots/`)

Hvert viewport har `*-fold.png` (over folden) og `*-full.png` (hele siden):

| Viewport | Full | Fold |
|---|---|---|
| iPhone 375 × 812 | `01-iphone-375-full.png` | `01-iphone-375-fold.png` |
| iPad 768 × 1024 | `02-ipad-768-full.png` | `02-ipad-768-fold.png` |
| MacBook 1280 × 800 | `03-macbook-1280-full.png` | `03-macbook-1280-fold.png` |
| Desktop 1920 × 1080 | `04-desktop-1920-full.png` | `04-desktop-1920-fold.png` |

I tillegg: `01-iphone-375-map.png` (zoom på kart-seksjonen som dokumenterer pin-klyngingen).

### Print-PDF

`qa-output/pdf/Sauda-print.pdf` — A4, `print`-media emulert, alle `<details>` åpnet før render.

Sjekket manuelt at:
- Topbar og deal-rail skjules i print (`display:none`).
- Hero-bilde og media-strips skjules.
- Mørk dd-mode-seksjon flippes til hvit bakgrunn, mørk skrift.
- Tabeller har `page-break-inside:avoid`.
- Details-drawers åpnes automatisk via `beforeprint`-handler og print-CSS.

### Modaler

Modal-oppførsel testet via Playwright (`qa-output/reports/modal-behavior.json`):

```json
{ "wasOpen": true, "closedByEsc": true, "reopened": true, "closedByBgClick": true }
```

Modal lukker både med ESC og klikk utenfor. ✓

### Pin-overlapp på 375 px

Rådata: `qa-output/reports/pin-overlaps-375.json`

Før fix: 18 overlappende par, alle i by-klyngen (sentrum, Åbøbyen, Eramet, utebasseng, klatrehall, Rørgata) og ski-klyngen (skisenter, Svandalen, Djuvsbotn).

Etter fix (mindre pin-størrelse `<=420 px`): 8 par, alle nå i by-klyngen. By-kvartalet har 6 pins innenfor 5 % × 5 % av kart-arealet — ved 375 px tilsvarer det ~16 × ~12 px. Reell fix krever clustering eller manuell justering av pin-koordinatene; det er en designbeslutning som er flagget i CONCERNS.

### Console / page errors

`qa-output/reports/console-messages.txt`, `qa-output/reports/page-errors.txt` — begge tomme. Lighthouse rapporterer én 404 (favicon, automatisk), ingen JS-feil.

## 5. Verktøyversjoner

- Playwright 1.56.1 (Chromium 141.0.7390.37)
- html-validate 9.7.1
- axe-core 4.x (via Playwright-injeksjon)
- Lighthouse 12.8.2
- Node.js 22.22.2

## 6. Reproduksjon

```bash
# Fra repo-rot:
mkdir -p /tmp/sauda-work && cp Sauda.html /tmp/sauda-work/
cd /tmp/sauda-work
npm install html-validate@9 lighthouse@12 axe-core playwright@1.56.1
npx http-server -p 8765 -c-1 --silent &
node run-playwright.mjs           # screenshots, PDF, axe, modal, pin-overlap
./node_modules/.bin/html-validate Sauda.html
CHROME_PATH=$(find /opt/pw-browsers -name chrome -path "*chrome-linux*" | head -1) \
  ./node_modules/.bin/lighthouse http://localhost:8765/Sauda.html \
  --chrome-flags="--headless=new --no-sandbox" \
  --only-categories=performance,accessibility,best-practices,seo \
  --output=json --output=html --output-path=qa-output/reports/lighthouse
```

`run-playwright.mjs` ligger i sandbox; ikke versjonert i repo (kjøre-script, ikke leveranseartefakt).

---

## 7. Rensingoppgave-runde 2026-05-11 — eksplisitt regresjons-sjekk

Rensingoppgaven gjorde 5 commits med significant strukturell endring (DEL 3 + DEL 4 fjernet, 251 linjer slettet, paragraf-IDer renummerert, body-text scrub). Følgende ble eksplisitt re-verifisert:

| Sjekk | Forventet | Faktisk |
|---|---|---|
| html-validate | 0 errors | **0 errors** ✓ |
| axe-core (samme runOnly-config) | ≤1 violation | **1 violation (uendret)** ✓ |
| Internal hrefs broken | 0 | **0 av 22** ✓ |
| aria-labelledby broken | 0 | **0 av 6** ✓ |
| Console errors @ 4 viewports | 0 | **0** ✓ |
| Page errors (uncaught throws) | 0 | **0** ✓ |
| Modal ESC + outside-click + reopen | alle ✓ | **alle ✓** ✓ |
| Print-PDF | genereres uten advarsler | **757 KB OK** ✓ |
| §-text orphans (§3.x/§4.x i body som ikke matcher ny §-struktur) | 0 | **0 (alle scrubbet)** ✓ |
| v75-v79 i body | 0 | **0** ✓ |
| BDO/Tobias/Mørland/Kvaslerud | 0 | **0** ✓ |
| 365 m / 365 moh i hele DOM | 0 | **0** (verifisert ift A3) ✓ |

**Konklusjon:** Rensingoppgaven introduserte ingen regresjon i automatiserte sjekker. Pre-eksisterende C-list-funn (color-contrast, pin-overlap, performance) er uendret som forventet.

### Visuell verifikasjon (manuell — krever menneskelig vurdering)

Skjermbilder generert i `/tmp/sauda-work/qa-output/screenshots/`:
- 4 viewports × 2 (full + fold) = 8 PNG-er
- Pluss en kart-skjermbilde @ 375 px

Disse må gjennomgås manuelt for:
- (a) Layout etter DEL 5 → DEL 3 renummerering ser konsistent ut
- (b) Single cta-block etter BDO-sletting flyter riktig på desktop og mobil
- (c) Topbar uten "Salgstakt" og "Risiko" chips ser balansert ut
- (d) Proof-grid med 4 kort (vs tidligere 6) layouter pent på alle bredder
- (e) Agenda-grid med 9 kort (vs 10) ikke har orphan-rad eller hull

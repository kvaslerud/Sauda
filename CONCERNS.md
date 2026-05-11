# CONCERNS — Sauda.html (pre-send review)

Branch: `claude/pre-send-review-zbFgK`

Alt under er funn som krever **din beslutning**. Jeg har ikke endret dem. Jeg har gått gjennom dokumentet som motpartens advokat. Det betyr at noen punkter er språklig pirk og noen er reelle faktakonflikter — jeg har markert hvert med kategori og kritikalitet.

Forkortelser:
- **A** = adresseres før utsending. Reell motstrid eller risiko for blowback i due diligence.
- **B** = bør avklares, men kan i prinsippet gå i print.
- **C** = svakhet jeg vil flagget, men du kan velge å la stå.

---

## A · Faktakonflikter som motparten vil finne

### A1 · Sauda Skisenter — bunn-høyde 320 vs 357 moh

| Sted | Tekst | Tall |
|---|---|---|
| Kart-tabell, `skisenter` (linje 1547, 1575) | "tretten kilometer alpinbakker fra 357 til 822 moh" | **357** |
| §1.7 Alpint-tabell (linje 1799) | "Bunn — ca. 320 moh" | **320** |
| §1.1 + agenda (337–822 og 357–578) | "Fra Kro (357 moh) til Djuvsbotn" | 357 |
| §4.1 risiko (1×), §5.6 (1×), Appendix F (1×) | "mildværsrisiko 357 moh", "357 moh sårbart" | 357 |

To muligheter:
1. Kro-stasjonen (gondol-bunn) ligger på 357 moh, mens den nederste piste-foten ligger på 320 moh. Da er begge tall riktige, men teksten i §1.7-tabellen og kart-beskrivelsen bør skille mellom dem.
2. Ett av tallene er feil.

**Beslutning du må ta:** Hvilket tall er riktig for "Sauda Skisenter, bunn"? Hvis (1), bør §1.7 Alpint-tabellen presisere "(piste-fot)" eller liknende.

### A2 · Sauda Skisenter — topp-høyde 822 vs ~850 moh

| Sted | Tall |
|---|---|
| Kart-tekst `skisenter` | "alpinbakker fra 357 til **822** moh" |
| §1.1 prosa (linje 1031) | "dagens topp på **~850** moh" |
| §1.7 Alpint-tabell (linje 1798) | "Topp — **ca. 850** moh" |

Forskjellen er 28 moh. Hvis "dagens topp" og "alpinbakker-topp" er ulike begreper (heisens topp-stasjon vs øverste preparerte løype) bør én av dem disambiguity-merkes. Ellers er én feil.

### A3 · Djuvsbotn "365 moh høyere enn dagens skisenterbunn"

Linje 1549, 1577: *"Snøsikkerhet **365 moh** høyere enn dagens skisenterbunn er hele forretningsplanens fundament."*

Djuvsbotn = 578 moh.
- Hvis bunn = 213 → +365 ✓. Men 213 forekommer ingen steder ellers.
- Hvis bunn = 357 (Kro) → +221 (det er BT1s velkjente høydeforskjell).
- Hvis bunn = 320 → +258.

Tallet **365 moh** matcher ingen av referansene i dokumentet. Mest sannsynlig type-feil: skulle vært **221 m** (BT1) eller **365 dager**-/365 ble blandet inn fra "året rundt" et annet sted.

**Adresseres:** Erstatt "365 moh" med korrekt verdi (sannsynligvis "221 m") eller verifiser opprinnelse.

### A4 · Statsforvalter — Vestland vs Rogaland

Sauda kommune ligger i Rogaland. BT2 Ravnafjell ligger i Sauda. Statsforvalteren med innsigelse mot BT2 er derfor **Statsforvalteren i Rogaland**.

| Sted | Tekst |
|---|---|
| §4.1 risiko-kilder (linje 2182) | "Statsforvalteren i **Rogaland** 2025" — riktig |
| §5.2 BT2-kilder (linje 2238) | *opprinnelig:* "Statsforvalteren i Vestland 2025" — **fikset til Rogaland** ✓ |
| §1.7 om Odda-prosjekt (linje 1824) | "Statsforvalteren i Vestland 2025" — Odda ligger i Vestland, så **korrekt** |

Fikset uten input fordi den ene endringen er åpenbar (§5.2 om Sauda kan ikke kilde Statsforvalter Vestland). **Bekreft at det stemmer at det er Statsforvalteren i Rogaland som har innsigelse mot BT2.**

### A5 · Appendix D · Søkt-kolonnens sum stemmer ikke med samletall

Linje 2443–2451:
- Ryfylkefondet 15 + Sparebankstiftelsen 13 + Hyttesalg 2 + Eramet 1 + Aksjonærer 7 + Banklån 10 + IN-lån 12 + Kommunelån "10 til 20" = **70–80 MNOK**
- "Samlet"-raden viser: "Søkt **~60**, Innvilget 27,5"

Enten dobbelttellingen mellom poster (f.eks. Eramet 1 inngår i Aksjonærer 7?), eller så er Søkt-totalt feil. Innvilget-summen 27,5 stemmer (15 + 8,5 + 2 + 2 = 27,5). Den uavklarte differansen er Søkt-kolonnens sum.

**Adresseres:** Avklar om Søkt-poster overlapper, eller om Søkt-totalt skal være ~75 MNOK.

### A6 · Portal Norge-undersøkelsen · n=1 144 vs subgrupper

Linje 1928: "1 144 respondenter (hytteeiere n=317, besøkende n=248, fastboende n=275, potensielle kjøpere n=29)"
- 317 + 248 + 275 + 29 = **869**
- 1 144 – 869 = **275 uplassert**

Enten finnes en femte gruppe (f.eks. "annet"), eller en av tallene er feil. Sammenfallet med fastboende n=275 ser ut som copy-paste-feil.

**Adresseres:** Avklar den manglende femte gruppen, eller korriger en av subgruppene.

### A7 · Skisenterets antall heiser — 5 vs 5 + 2 skibånd vs 7

| Sted | Tekst |
|---|---|
| Kart-beskrivelse `skisenter` | "**Fem heiser, to skibånd**" (totalt 7 transportenheter) |
| §1.7 Alpint-tabell | "Heiser — **5 skitrekk**" (samme 5? eller 5 av 7?) |

Hvis Sirdal-raden "9 (inkl. Sør-Rogalands eneste stolheis)" teller skibånd, må Sauda telle alle 7. Hvis Sirdal-tallet bare er heiser i streng forstand, må Sauda-tallet være 5. Inkonsistent semantikk gir feil oppfattet sammenligning.

**Adresseres:** Avklar telleregel. Mest ærlig: "5 skitrekk + 2 skibånd" for Sauda, "9 heiser (inkl. 1 stolheis) + 0 skibånd" for Sirdal.

---

## B · Påstander uten tydelig kilde eller kalibrering

### B1 · "Anslag 1:5 til 1:11 på investert gondolkrone vs hyttekroneverdi"

§"Hvorfor dette er interessant" (linje 753) og §2.1 (linje 1882):
*"Prosjektgruppens anslag er 1:5 til 1:11 på investert gondolkrone vs hyttekroneverdi."*

§5.6 / Appendix F kvalifiserer: *"Hafjell 2006 og Myrkdalen-historikk som referanser."* Men intervallet 1:5–1:11 er ikke begrunnet med tall eller kildereferanse. Dette er en bred multippel som vil bli spurt om i DD.

### B2 · "Estimat 30 til 80 MNOK kumulativt over 5 til 10 år" for markedsføring

§2.2 (linje 1916): Estimat med 2,67× spennvidde og 2× horisont-spennvidde, ingen kilde. Indikativ splitt "partner ~50 %, Sauda Vekst ~30 %, destinasjonsaktørene ~20 %" framstår dratt fra hatten.

### B3 · "+10,8 % / +10,5 % / +10,3 %" boligprisvekst Stavanger 2024

§1.4 callout (linje 1187): Tre presise tall uten kilde i blokken. Kildelisten under (linje 1189) inneholder ikke Eiendom Norge for de spesifikke delmarkedene.

### B4 · "Sommerbesøk +113 % over 3 år" Hafjell

§2.1 (linje 1849, 1882): Tall ført til SkiStar årsrapport, men ingen henvisning til hvilken rapport. "1 av 4 sommergjester hadde aldri vært der om vinteren" mangler kilde helt.

### B5 · "Reiselivskartlegging 2020 (basert på 2019-data) anslo 172 000 overnattinger, 120 MNOK i lokal omsetning og 93 arbeidsplasser"

§1.5 (linje 1200): Tall tilskrevet "Prosjektgruppen / reiselivskartlegging 2020", men ingen rapporttittel eller utfører. Vil bli spurt etter i DD.

### B6 · "Vurdering for avanserte skikjørere — Vertikalen er 60 prosent større"

§1.7 (linje 1821). Hvis Sauda er 500 m og Sirdal 300 m, er forskjellen 66,7 %, ikke 60 %. Hvis Sauda er 465 m (357→822) og Sirdal 328 m (600→928), er forskjellen 41,8 %. Tallet "60 prosent" lar seg ikke utlede.

### B7 · "Anslått besøkende per år · Kun BT1 50 000 til 115 000 · Med BT2 120 000 til 200 000+"

§5.2 (linje 2232): Bredt anslag uten metodikk eller kilde. Appendix F kvalifiserer som "anslag" men gir ikke grunnlag.

---

## C · Designvalg jeg vil flagget

### C1 · Topbar-versjon — opprinnelig "Mai 2026", endret til "April 2026"

Topbar (linje 667) sto opprinnelig som **"v79 · Mai 2026"**. Alle andre 18 datoreferanser i dokumentet bruker "April 2026" / "april 2026" inkludert footer, hero, og 14 kildelister. Jeg fikset topbar til "April 2026" som standardisering. **Bekreft.**

### C2 · Pin-overlapp på 375 px (8 par igjen etter fix)

By-pin-klyngen (sentrum, Eramet, utebasseng, klatrehall, Åbøbyen, Rørgata) overlapper fortsatt på iPhone-bredder selv etter pin-størrelsen er redusert. Hardcodede koordinater i `LOCATIONS` (linje 1568+) plasserer 6 pins innenfor x: 73–82, y: 28–38, og det er for tett uansett pin-størrelse.

**Mulige tiltak (krever beslutning):**
- (a) Reposisjoner pins manuelt med små x/y-justeringer for å spre klyngen.
- (b) Implementer enkel clustering (kombiner overlappende pins under én "By"-pin på små viewports).
- (c) La klyngen stå — kortene under kartet gjør at brukeren uansett kan navigere til hver lokasjon. Jeg har sjekket: kortet-navigering fungerer.

Anbefaler (a) eller (c). (b) er en JS-utvidelse som krever en utviklerrunde.

### C3 · Color-contrast — 177 noder fortsatt under WCAG AA-terskel

Etter fix (mørk dd-mode er fikset, ratio 1.11 → grei). Resten er typografisk hierarki:
- 45 × `.section-num` (kobber `#b8602d` på papir, ratio 3,92 — failer for body, passer for stor tekst)
- 25 × `.sources` (kildefotnoter, ratio 2,65)
- 10 × `.figure-note` (figur-undertekst, ratio 2,63)
- 10 × `.callout em`-aksent
- 8 × `.deal-card .label` (3,92)
- 7 × `.proof-card .metric` (lys kobber `#b68a5b` på papir, ratio 2,74)
- 6 × `.myr-head/.myr-point .yr`
- 5 × `.deal-room-kicker`
- 5 × `.media-strip .cap-label`
- 3 × `.bridge-row span`
- 3 × footer-undertekst (ratio 4,47 — like under 4,5)
- 3 × `.ok` status-chip
- 2 × `.pipe-sold-label`
- 1 × `.watermark` (avhengig av background-position; aria-hidden satt)

Dette er **designvalg**. Hvis du vil at memo-en skal være streng WCAG 2.1 AA: alle sekundærtekster må mørkne med ca. 15–25 %. Det vil flate ut typografisk hierarki og gjøre dokumentet visuelt mer "rapport, mindre cinematic". Anbefales ikke uten eksplisitt mandat.

### C4 · Performance 54/100 — selvinneholdt fil med base64-bilder

`.html`-filen er 2,8 MB. Alle bilder er base64-innleirede JPEG. Lighthouse rapporterer 15,0 s FCP/LCP fordi alle bytes må parses før første render.

**Mulige tiltak:**
- (a) La filen være selvinneholdt. Performance-score ignoreres ved manuell levering (PDF eller email-vedlegg). Brukerens nettverk ser ikke 15 s, de ser én sekundær lokal fil-åpning.
- (b) Split ut bilder til separate `.jpg`-filer i samme mappe. Performance løftes til 90+. Men bryter "én fil"-leveransen.

Anbefaler (a) gitt at leveransekanalen er én fil og ikke web hosting.

### C5 · "Sjelden elsker hele familien ski. Sauda krever ikke at de gjør det."

§1.5 (linje 1199). Setningskonstruksjonen er glatt, ufaglig — selv om budskapet er riktig. Vurder om dette skal i et investor-memo eller om det hører hjemme i salgsmateriell. Du eier stemmen.

### C6 · "Norsk gårdsromantikk uten Disney-versjonen."

§Kart Tveit Tunet (linje 1554, 1583). Vakker formulering, men slipping for et tørt investor-memo. Behold hvis bevisst valg.

### C7 · "Det andre fjelldestinasjoner bruker milliarder på å bygge fra grunnen, finnes allerede her."

§Kart sentrum (linje 1541, 1569). "Milliarder" uten henvisning. Lett demper: "hundretalls millioner" eller fjern kvantifisering.

### C8 · "naturlig overlegen" (snøkvalitet, §1.7 linje 1812)

Ord som "naturlig overlegen" er rødt klut for skeptisk leser. Vurder "naturlig fortrinn" eller "topografisk fordel".

---

## Ikke-funn (du kan slappe av på disse)

Disse sjekkene fant ingenting:
- Interne lenker (`href="#..."`): alle 18 anker peker på eksisterende IDer. Ingen brutte.
- Modaler: lukker både med ESC og utenfor-klikk. Verifisert via Playwright.
- Print-PDF: 38 sider, dark-mode flippes til hvitt, drawers åpnes, tabeller har page-break-inside:avoid. Ingen "side-skift midt i tabell" observert i automatisert kjøring.
- Stedsnavn (Svandal, Djuvsbotn, Ravnafjell, Hustveitsåta, Hovlandsnuten, Allmannajuvet): alle stavet konsekvent.
- Stavefeil `fjelllandskap` (3 l-er) → fikset til `fjellandskap` (kart-tekst, 2 forekomster).
- Skisenter åpningsår 1968, Eramet 1915 + "111 år": konsistent og matter (2026 – 1915 = 111).
- "~500 enheter" feltsum: H9 ~310 + Nord ~70 + BAA1-2 ~30 + BAA4-5 inntil 53 + Djuvsbotn/Stølshaugen ~44 = **507**, avrundet til ~500. Konsistent.
- Brutto salgsverdi ~2,6 mrd: 500 × 95 × 55 000 = 2 612 500 000. Stemmer.
- Utviklingsbidrag 286 500 kr: 5 225 000 – 4 275 000 – 350 000 – 313 500 = 286 500. Stemmer.
- 225 enheter × 286 500 ≈ 64 MNOK: 64 462 500. Stemmer (avrundet).
- 27,5 av 60 MNOK = 45,8 % ≈ 46 %: stemmer.
- Realiseringshorisont 500/15 = 33,3 år; 500/25 = 20 år: stemmer.
- Myrkdalen 79 400 / 15 000 = 5,29× ≈ 5,3×: stemmer.

---

## Fikset uten input (full liste i PR-beskrivelse)

Disse var entydige feil og er fikset:
1. Topbar "Mai 2026" → "April 2026" (matcher hele resten av dokumentet).
2. Meteorologisk institutt normalperiode i §1.6-kilde: "1981 til 2020" → "1991 til 2020" (matcher prosa-teksten 5 linjer over).
3. Statsforvalteren for BT2 (§5.2-kilder): "Vestland" → "Rogaland" (Sauda er i Rogaland).
4. Stavefeil "fjelllandskap" → "fjellandskap" (2 steder, kart-tekst og JS-data).
5. HTML/a11y-fikser (sjekklisten i QA-REPORT.md). Ingen tekstendring.

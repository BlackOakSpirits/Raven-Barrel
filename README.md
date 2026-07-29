# Raven & Barrel — website

Statische website met leeftijdspoort (18+), winkelpagina, ons verhaal, The Oak Circle, Limited Edition en FAQ. Geen build, geen framework: alles zit in `index.html`.

## Live zetten via GitHub Pages

**1. Repository aanmaken**
Ga naar github.com → **New repository**. Noem hem bijvoorbeeld `raven-and-barrel`. Zet hem op **Public** (Pages werkt alleen gratis bij publieke repo's). Niet aanvinken: README, .gitignore, license — die zitten hier al in.

**2. Bestanden uploaden**
Op de lege repo-pagina: **uploading an existing file** → sleep álle bestanden uit deze map erin (ook `.nojekyll`, die is verborgen — zet in Finder ⌘⇧. aan, in Windows Explorer "Verborgen items" aan). Klik **Commit changes**.

Liever via de terminal:
```bash
git init
git add .
git commit -m "Eerste versie"
git branch -M main
git remote add origin https://github.com/JOUWNAAM/raven-and-barrel.git
git push -u origin main
```

**3. Pages aanzetten**
Repo → **Settings** → **Pages** → bij *Source* kies **Deploy from a branch** → branch `main`, map `/ (root)` → **Save**.

Na ongeveer een minuut staat je site op:
`https://JOUWNAAM.github.io/raven-and-barrel/`

Ververs de pagina als je eerst een 404 ziet; de eerste deploy duurt even.

**4. Eigen domein (optioneel)**
Heb je bijvoorbeeld `ravenandbarrel.nl`, zet dan bij je domeinprovider:

| Type | Naam | Waarde |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | JOUWNAAM.github.io |

Vul het domein daarna in bij **Settings → Pages → Custom domain** en vink **Enforce HTTPS** aan zodra dat kan.

## Iets wijzigen

Alles staat in `index.html`. Klik het bestand aan op GitHub, klik het potloodje, pas aan, **Commit changes** — binnen een minuut staat de wijziging live.

Waar je waarschijnlijk begint:
- **Producten**: zoek op `<article class="label">`. Naam, prijs (`data-price`), proefnotitie en batchgrootte staan bij elkaar.
- **Kleuren**: bovenaan in `:root` (`--copper`, `--wax`, `--patina`).
- **KvK en btw-nummer**: onderaan in de footer, daar staan nu nullen.
- **Teksten van het zegel**: zoek op `id="gate"`.

## Wat deze site wel en niet doet

**Wel:** leeftijdspoort die de keuze 30 dagen onthoudt, alle vijf de pagina's met deelbare links (`#/faq`, `#/circle`), werkende winkelwagen, FAQ-accordeon, mobiel menu.

**Niet:** afrekenen en e-mails opslaan. Dat kan een statische site niet — er is geen server. Twee routes:

- **Betalen**: koppel de knop *Afrekenen* aan een betaallink (Mollie Payment Links, Stripe Payment Links) of zet de winkel alsnog in Shopify en gebruik deze site als merkwebsite die doorlinkt.
- **The Oak Circle**: maak een gratis formulier bij Mailchimp, MailerLite of Brevo en vervang het `<div class="form-card">`-blok door hun embed-code. Houd het 18+-vinkje erin.

## Leeftijd — de twee plekken die tellen

De poort bij binnenkomst houdt niemand tegen die liegt; juridisch leunt het zwaartepunt in Nederland op de controle **bij aflevering**. Regel bij je bezorger een 18+-verzendmethode met ID-scan (PostNL Alcoholservice, DHL Age Check), zet afhaalpunten uit, en houd de vermelding op de site zoals hij nu op vier plekken staat: bovenbalk, productblok, winkelwagen en footer.

Voor online verkoop van sterke drank heb je bovendien een **slijtersvergunning** nodig. Check dat bij je gemeente vóór je verkoopt.

## Bestanden

| Bestand | Waarvoor |
|---|---|
| `index.html` | De hele site: HTML, CSS en JavaScript |
| `favicon.svg` | Het zegel als tabbladicoon |
| `404.html` | Stuurt onbekende paden terug naar de winkel |
| `robots.txt` | Geeft zoekmachines toestemming |
| `.nojekyll` | Zegt GitHub Pages dat het de bestanden ongewijzigd moet serveren |

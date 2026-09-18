# Ultima — website

Statische website (HTML/CSS/JS, geen framework, geen backend). 19 pagina's, zie hieronder.

## Live zetten via GitHub + Vercel

1. **GitHub**
   - Maak een nieuwe (lege) repository aan op GitHub.
   - Pak deze map uit en push de inhoud naar die repository (bijvoorbeeld met GitHub Desktop, of via de terminal: `git init`, `git add .`, `git commit -m "Eerste versie Ultima-site"`, `git remote add origin <repo-url>`, `git push -u origin main`).

2. **Vercel**
   - Log in op [vercel.com](https://vercel.com) en klik op "Add New… → Project".
   - Selecteer de zojuist gepushte GitHub-repository.
   - Framework preset: kies **"Other"** (geen build-stap nodig).
   - Build command: laat leeg. Output directory: laat leeg / `.` (root) — dit is een pure statische site.
   - Klik op **Deploy**. Na een paar seconden staat de site live op een `*.vercel.app`-domein.
   - Wil je een eigen domein? Voeg 'm toe onder Project → Settings → Domains.

Elke volgende `git push` naar de hoofdbranch zet automatisch een nieuwe versie live.

## Structuur

- `index.html`, `over-ons.html`, `producten.html`, `dealers.html`, `contact.html`
- Categoriepagina's: `boxsprings.html`, `matrassen.html`, `topmatrassen.html`, `ledikanten.html`, `kussens.html`
- Subpagina's (één niveau dieper, niet in hoofdnav): `matrassen-initio.html`, `matrassen-cumlaude.html`, `topmatrassen-initio.html`, `topmatrassen-cumlaude.html`, `kussens-aw.html`, `kussens-discus.html`, `kussens-atlas.html`, `kussens-balans.html`, `hoofdborden.html` (subpagina van Boxsprings)
- `assets/` — logo, favicons, productfoto's
- `css/style.css` — alle styling
- `js/main.js` — mobiele navigatie, lichtbox voor productfoto's, dealerzoeker + kaart, contactformulier (front-end only)
- `vendor/leaflet/` — kaartbibliotheek voor de dealerspagina (lokaal gehost, geen build-stap nodig)

## Bekende openstaande punten

- Contactformulier is front-end only, nog niet aan een echte backend/e-mailservice gekoppeld.
- Sommige dealers missen nog een e-mailadres (niet in brondata).
- Overige productdata kussens (afmetingen/hoogtes) nog aan te vullen.
- De dealerzoeker gebruikt Nominatim (OpenStreetMap) voor het omzetten van een getypte plaatsnaam naar coördinaten wanneer er geen directe naam-/plaatsmatch is — een gratis publieke API, prima voor dit volume maar bij hoge bezoekersaantallen kan een eigen geocoding-dienst nodig zijn.

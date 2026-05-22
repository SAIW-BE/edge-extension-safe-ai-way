# Landing page voor Edge-installatie

Deze map bevat de landingspagina voor BYOD-installatie van Safe AI Way op Microsoft Edge. Bedoeld voor de saiw-be GitHub Pages hosting.

## Inhoud

```
landing/
├── index.html                    Landingspagina (web + print-versie)
├── safe-ai-way-edge-v2.1.0.zip  Symlink / kopie van releases/...zip
└── screenshots/                  PNG-screenshots voor de stappen
    ├── step-1-unzip.png         Rechtsklik → Alles uitpakken
    ├── step-2-edge-extensions.png  edge://extensions pagina
    ├── step-3-dev-mode.png      Ontwikkelaarsmodus toggle aan
    ├── step-4-drag-folder.png   Mapje slepen / Uitgepakte versie laden
    └── step-5-pin.png           Icoon in toolbar
```

## Screenshots maken

De HTML toont placeholder-tekst zolang de screenshots niet bestaan. Voor de demo wil je échte screenshots. Gebruik **Windows + Shift + S** of **Cmd + Shift + 4** (macOS):

1. **step-1-unzip.png** — Verkenner met rechtsklik-menu op het ZIP-bestand → toon de "Alles uitpakken…" optie gemarkeerd.
2. **step-2-edge-extensions.png** — Edge geopend op `edge://extensions/` (lege staat, geen extensies geladen, of met andere extensies). Toon vooral de URL-balk + linker zijbalk.
3. **step-3-dev-mode.png** — Close-up van de **Ontwikkelaarsmodus**-toggle linksonder, in AAN-stand. Liefst met een rode cirkel/pijl rondom.
4. **step-4-drag-folder.png** — Twee opties: (a) drag-en-drop animatie waarbij een mapje vanuit Verkenner over de Edge-pagina zweeft, of (b) close-up van de **"Uitgepakte versie laden"** knop bovenaan met markering.
5. **step-5-pin.png** — Edge toolbar met het puzzelstukje opengeklapt en het Safe AI Way-icoon met pin-knop, of het icoon uiteindelijk vastgepind aan de toolbar.

**Tips:**
- Gebruik altijd hetzelfde Edge-thema (light of dark) voor consistentie
- Liever Nederlandstalige Edge UI dan Engels (matcht de instructie-tekst)
- Schaal screenshots niet groter dan 1200px breed (verdubbelt anders de pagina-grootte)
- Optimaliseer met tinypng.com of squoosh.app vóór upload

## Deploy naar GitHub Pages

In de saiw-be repo (root van `edge-extension-safe-ai-way`):

```bash
# Vanuit de geklonde saiw-be repo
cp /pad/naar/landing/index.html .
cp /pad/naar/landing/safe-ai-way-edge-v2.1.0.zip .
cp /pad/naar/landing/safe-ai-way-edge-v2.1.0.crx .
cp /pad/naar/landing/update.xml .
mkdir -p screenshots && cp /pad/naar/landing/screenshots/*.png screenshots/

git add .
git commit -m "Landing page + v2.1.0 release"
git push origin main
```

Na 1-5 minuten beschikbaar op:
- **Landingspagina:** `https://saiw-be.github.io/edge-extension-safe-ai-way/`
- **Download (ZIP):** `https://saiw-be.github.io/edge-extension-safe-ai-way/safe-ai-way-edge-v2.1.0.zip`
- **MDM update manifest:** `https://saiw-be.github.io/edge-extension-safe-ai-way/update.xml`
- **MDM CRX:** `https://saiw-be.github.io/edge-extension-safe-ai-way/safe-ai-way-edge-v2.1.0.crx`

Voor de school-demo deel je enkel de landingspagina-URL (of QR-code daarvan).

## QR-code voor projectie / handout

Genereer met bv. qr-code-generator.com of locaal:

```bash
# Met qrencode CLI (brew install qrencode)
qrencode -o qr-install.png -s 10 "https://saiw-be.github.io/edge-extension-safe-ai-way/"
```

## Print-versie (handout)

De pagina heeft ingebouwde `@media print` CSS die:
- De FAQ-sectie verbergt
- Stappen compacter maakt
- Past op één A4

In Edge: druk **Ctrl+P** → A4 → Marges: Normaal → Print of "Opslaan als PDF". Geen aparte handout-file nodig.

## Te updaten bij nieuwe versie

Zoek + vervang `2.1.0` in `index.html` voor de nieuwe versie. Hetzelfde voor de .zip-bestandsnaam.

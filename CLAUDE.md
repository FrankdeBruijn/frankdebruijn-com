# frankdebruijn.com

Persoonlijke onepager van Frank de Bruijn ("Het onzichtbare in beeld"). Sinds 28-10-2026 de
enige website die Frank nog heeft: artofslowmotion.com (en straks orangestock.com) verwijzen
hierheen door.

## Stack
- Eén statische pagina: `public/index.html` plus `public/assets/` (css, fonts, icons, img)
- Astro doet alleen de build (kopieert `public/` naar `dist/`); er zijn geen Astro-pagina's.
  Zo bleven de build-instellingen van Cloudflare Pages ongewijzigd.
- Gehost op Cloudflare Pages — elke push naar `main` deployt automatisch

## Herkomst
`public/index.html` is op 28-10-2026 geëxporteerd uit de WordPress-subsite op het
orangestock-pakket (thema `frankdebruijn`, staat in de repo `orangestock/theme/frankdebruijn`).
Bij de export zijn de asset-URL's naar `/assets/` omgezet en is alles weggehaald wat alleen voor
WordPress bestond (feeds, oEmbed, wp-json, speculationrules). De inline `<style>`-blokken zijn
WordPress' blokstijlen en zijn nodig voor de layout — niet weghalen.

De oudere Astro-site met meerdere pagina's (nagebouwd naar Wix) staat in de git-geschiedenis vóór
de branch `onepager`.

## Lokaal
```bash
npm run build                      # dist/
python3 -m http.server -d dist     # bekijken op http://localhost:8000
```

## Contact (staat in de pagina)
- Telefoon: 06 12415418
- E-mail: frankdebruijn@me.com (alle mail aan @frankdebruijn.com komt daar ook binnen,
  via Cloudflare Email Routing)

## Let op bij aanpassen
- De foto-tegels laden pas bij scrollen; een full-page screenshot zonder scrollen toont ze leeg.
- `og:image` moet een absolute URL blijven, anders geen preview op LinkedIn/WhatsApp.
- Controleer na elke wijziging op telefoonbreedte (390 px).

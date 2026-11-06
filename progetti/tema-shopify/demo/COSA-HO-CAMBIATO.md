# Cosa ho cambiato (copia locale, 30 settembre 2026)

Il sito live **non** è stato aggiornato. Nessun accesso a Shopify admin o al Mac. Solo i file sotto `/workspace/tecnobici-theme`.

La home non è un template JSON: l’ordine resta `config/settings_data.json` → `current.content_for_index`. Non ho aggiunto né tolto sezioni da quell’elenco.

## Foto copiate in `assets/`

Dalle foto studio in `/workspace/tecnobici-home/assets/`:

- `assets/home-bici-city-kit.png`
- `assets/home-bici-mtb-rossa.png`
- `assets/home-bici-mtb-grigia.png`
- `assets/home-kit-triangolo.png`
- `assets/home-kit-studio-ufficiale.png`
- `assets/home-kit-hyanite.png`
- `assets/home-kit-custodia.png`

Hyanite e custodia sono nel tema ma **non** sono state messe in home, per non attribuirle a Tongsheng o Bafang.

## Dove punta ogni foto

Slideshow (stesse 3 slide, stessi testi e link):

| Slide | Foto | File |
| --- | --- | --- |
| KIT PIANURA (sinistra) | bici city azzurra + kit argento | `home-bici-city-kit.png` |
| KIT PASSO (centro) | motore + borsa triangolo | `home-kit-triangolo.png` |
| KIT CIMA (destra) | MTB rossa + kit triangolo | `home-bici-mtb-rossa.png` |

Blocchi TONGSHENG e BAFANG (stessi due blocchi; foto grande e foto piccola uguali, perché per ogni marchio c’è una sola foto studio assegnata):

| Blocco | Foto | File |
| --- | --- | --- |
| TONGSHENG | motore + batteria verticale alta (kit ufficiale) | `home-kit-studio-ufficiale.png` |
| BAFANG | motore + borsa triangolo | `home-kit-triangolo.png` |

Le impostazioni immagine di Shopify sono un selettore (`image_picker`), non un URL libero. In `settings_data.json` ora c’è il nome del file in `assets/`. Nel liquid, se Shopify non lo trasforma in immagine, si usa `asset_url`.

## Testo e colori (solo il minimo)

- Sulle tre slide il testo era bianco (`#ffffff` / `#e5e5e5`), pensato per le foto scure vecchie. Sulle foto studio chiare non si leggeva. Titolo `#1a1a1a`, sottotitolo `#333333`, bottone `#1a1a1a`. I testi italiani delle slide non sono stati riscritti.
- Banner `section-banner-v1`: sul sito live **non** viene stampato, ma in questa copia era ancora in homepage e senza foto mostrava placehold.it con «End of season clearnce». L’ho nascosto con `display:none` (la sezione resta nell’elenco). Il testo salvato, se un giorno si riaccende, è: titolo «Montaggio in officina a Este», sottotitolo «Porta la tua bici: il kit si monta da noi, a Este.», bottone «CONTATTACI» verso la pagina contatti. Foto di quel banner (nascosto): `home-bici-mtb-grigia.png`. Nessun prezzo inventato.
- Loghi `section-brand-v1`: nascosti con `display:none`, perché i 6 blocchi non hanno immagine e mostravano placehold.it. Non ho tolto la sezione.
- Instagram (`section-intagram-v2`) lasciato com’è: non usa placehold.it su questo negozio. Sul sito live quella sezione non compare.
- Non toccati: schede «I più richiesti» (collezione `hp-venduti`), Google Reviews, header, footer, barra promo.

## Nota sul menu

L’header della home è il v4, trasparente, con logo e menu bianchi, fatti per stare sopra le slide scure. Con queste foto chiare, in cima alla pagina il menu può risultare poco leggibile finché non diventa sticky (sfondo `#1e1e1e`). Non l’ho modificato.

## File toccati

- `config/settings_data.json`
- `sections/section-slideshow-v1.liquid`
- `sections/section-collection-v6.liquid`
- `sections/section-banner-v1.liquid`
- `sections/section-brand-v1.liquid`
- `assets/home-*.png` (nuovi)
- `preview/homepage.html` (anteprima statica, non è il tema)
- `preview/logo-w.png` (logo già online, solo per l’anteprima)
- `preview/homepage-desktop.png`

## Anteprima

Aprire `preview/homepage.html` (serve una cartella servita in locale, oppure il file diretto se il browser carica gli script del tema). Ordine come la home live: promo, menu, slideshow, I più richiesti, Tongsheng/Bafang, recensioni. Le schede prodotto nell’anteprima sono una fotografia del sito del 30 settembre 2026, non una modifica al tema. Lo screenshot è `preview/homepage-desktop.png` (lo slider era sulla slide KIT PASSO).

La prima slide (KIT PIANURA, quella all’apertura) è la MTB rossa `home-bici-mtb-rossa.png`; la bici city è passata su KIT CIMA.

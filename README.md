# Salumi DOP Piacentini – Realtà Aumentata

Esperienza AR (MindAR + A-Frame) per la pagina del libro "C'è un Paese dove da sempre si fanno capolavori alimentari…".
Funziona su iPhone (Safari) e Android (Chrome), senza app.

## Pubblicazione su GitHub Pages
1. Crea un nuovo repository su GitHub (es. `ar-salumi`).
2. Carica **tutti** questi file (trascinali in "Add file → Upload files"):
   ```
   index.html
   targets.mind
   logo-consorzio.png
   panini.png
   salumi-pagina.png
   aframe-1.5.0.min.js
   mindar-image-aframe-1.2.5.prod.js
   ```
   Tutti i file vanno nella cartella principale del repository (nessuna sottocartella).
. Settings → Pages → Source: "Deploy from a branch" → branch `main`, cartella `/ (root)` → Save.
4. Dopo 1–2 minuti il sito è su `https://TUO-UTENTE.github.io/ar-salumi/`.
5. Genera il QR code con quell'indirizzo (deve essere **https**, altrimenti la fotocamera non parte).

## Cosa succede
- I salumi compaiono in AR sopra quelli stampati.
- Il logo arriva dall'angolo in alto a destra ruotando e si posa sul logo stampato → link al sito welcome.
- Sotto i salumi: i panini (→ sito welcome) e il rettangolo rosso "Scopri tutte le nostre ricette gourmet" (→ pagina ricette).
- Pizzica con due dita per ingrandire (0,6× – 3,5×); il pulsante "Dimensione originale" ripristina.
- Se la pagina esce dall'inquadratura per più di 2 secondi, l'animazione riparte al ritorno.

## Regolazioni rapide (in index.html)
- Stabilità: `filterMinCF` / `filterBeta` nell'attributo `mindar-image` e `alpha` del componente `pose-smoother`
  (più basso = più fermo ma più "lento" a seguire).
- Posizione/dimensione di panini e rettangolo: attributi `position`, `width`, `height` di `#panini` e `#cta`
  (unità: larghezza della pagina = 1; centro pagina = 0,0).

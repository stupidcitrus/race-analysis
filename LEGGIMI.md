# Race Analysis · Phi!Number — sito con più regate

```
index.html                                           l'app
data/races.json                                      l'elenco delle regate (i pulsanti della home)
data/race-2026-11-15-44cup-cartagena-2026-race-10.json   una regata (un file per regata)
data/onboard.json                                    le partenze lette dai log di bordo, di tutti i giorni
```

Password per Load KML, Load log, Clear ed Export: **Phi-spinnaker-259**

---

## Aggiornare il sito già pubblicato (passaggio a questa versione)

1. Nel repository su GitHub carica, sostituendo i vecchi, **index.html** e tutto il contenuto della cartella **data** di questo zip (**Add file → Upload files**, poi **Commit changes**).
2. Se vuoi, cancella i file vecchi che non servono più: `data/race.json` e `data/example-cartagena-r10.json`.

## Aggiungere una nuova regata

1. Apri il sito e premi **Load KML** (password). Carica i KML della regata, uno per barca.
2. Se hai il log di bordo di quel giorno, premi **Load log** e caricalo. Un solo log per giorno basta per tutte le regate del giorno.
3. Controlla ora di partenza, TWD e numero di lati.
4. Premi **Export for website**. Il browser scarica:
   - `race-<data>-<nome>.json` → la nuova regata
   - `races.json` → l'elenco aggiornato (con le regate di prima più la nuova)
   - `onboard.json` → solo se hai caricato un log
   Se il browser chiede di consentire download multipli, accetta.
5. Su GitHub apri la cartella **data**, poi **Add file → Upload files**, trascina tutti i file scaricati e premi **Commit changes**.
6. Dopo circa 1 minuto la home del sito mostra un pulsante in più. Le regate di prima restano.

Se aggiungi più regate di fila senza ricaricare la pagina, carica su GitHub i file dell'**ultimo** Export: il `races.json` più recente le contiene tutte.

## Correggere una regata già pubblicata

Aprila dalla home, inserisci la password (per esempio premendo Load KML e poi Annulla), correggi ora di partenza, TWD o lati e premi **Export for website**. Ricarica i due file su GitHub.

## Come vengono usati i log

Il log di un giorno contiene tutte le partenze di quel giorno: l'app le trova dal timer di regata. In ogni regata la tabella "Onboard start data" mostra le partenze di quel giorno ed evidenzia quella con l'ora più vicina (entro 10 minuti). Se l'ora di partenza della regata era solo stimata dalle tracce, viene sostituita con quella esatta del log.

## Prima pubblicazione su GitHub Pages

1. Account su github.com (il nome utente entra nel link).
2. **New repository** → nome `race-analysis`, **Public** → **Create repository**.
3. **Add file → Upload files**: index.html e la cartella data → **Commit changes**.
4. **Settings → Pages** (se Settings non si vede, è nel menu "…") → Source: **Deploy from a branch** → **main** / **(root)** → **Save**.
5. Link: `https://NOMEUTENTE.github.io/race-analysis/`

## Da sapere

- La password blocca i pulsanti, ma in un sito statico il codice è leggibile. Quello che vedono gli altri cambia solo quando **tu** carichi i file su GitHub.
- Con un repository pubblico, i file delle regate sono scaricabili da chi conosce il link.

# Race Analysis 44Cup Cartagena · Phi!Number — sito con più regate

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
   Se le boe o la linea di partenza non sono nel punto giusto: nella sezione **Map and replay** premi **Edit marks**, trascina Pin, RC e le boe nella posizione corretta e premi **Done editing**. In alternativa, sotto la mappa compare una tabella con latitudine e longitudine di Pin, RC, boe e arrivo: scrivi gradi e primi con decimali, come sulla carta (`37° 32.316' N` e `1° 1.710' W`: gradi nel primo campo, primi nel secondo, N/S o E/W dal menu) e premi Invio. L'analisi si ricalcola. **Reset marks** torna alle posizioni automatiche.
   Il segno tra L2 e L3 (e in generale alla fine di ogni lato di poppa che non è l'arrivo) è un **cancello** con due boe, *Gate 2 · left* e *Gate 2 · right*, sinistra e destra guardando sottovento (come le vede chi arriva in poppa). Sulla mappa, orientata con il vento dall'alto, la boa sinistra appare quindi a destra.
   **Arrivo:** finché non tocchi la boa d'arrivo, l'ordine d'arrivo è stimato dal calo di velocità dopo il traguardo. Se sposti o scrivi la posizione di *Finish · mark*, l'arrivo diventa il momento in cui ogni barca taglia la linea d'arrivo. Per avere la linea esatta inserisci anche *Finish · committee boat*; senza, la linea passa dalla boa perpendicolare all'ultimo lato. Una barca che non taglia la linea risulta non arrivata.
4. Premi **Export for website**. Si apre un riquadro con un pulsante **Download** per ogni file: premili tutti.
   - `race-<data>-<nome>.json` → la nuova regata
   - `races.json` → l'elenco aggiornato (con le regate di prima più la nuova): **senza questo il pulsante non compare**
   - `onboard.json` → solo se hai caricato un log
   Con Chrome o Edge sul computer puoi usare invece **Save all to a folder…**: scegli una volta la tua cartella `data` (per esempio una copia sul computer) e i file vengono scritti lì con il nome esatto, sostituendo i vecchi, senza copie "(1)".
5. Su GitHub apri la cartella **data**, poi **Add file → Upload files**, trascina tutti i file scaricati e premi **Commit changes**.
6. Dopo qualche minuto (GitHub può impiegare fino a 10 minuti ad aggiornare) la home mostra un pulsante in più. Le regate di prima restano. Se non lo vedi, ricarica con Ctrl+F5 (Cmd+Shift+R su Mac).

Se aggiungi più regate di fila senza ricaricare la pagina, carica su GitHub i file dell'**ultimo** Export: il `races.json` più recente le contiene tutte.

## Eliminare una regata

1. Apri la home del sito e premi **Manage races (owner)** in fondo alla pagina, poi inserisci la password.
2. Sotto la regata da togliere premi **Remove from site** e conferma.
3. Premi **Download**: scarica il nuovo `races.json` senza quella regata.
4. Su GitHub, nella cartella **data**: **Add file → Upload files**, carica `races.json` (sostituisce il vecchio), **Commit changes**.
5. Facoltativo: apri il file della regata (`race-….json`), premi **…** in alto a destra → **Delete file** → **Commit changes**.

## Correggere una regata già pubblicata

Aprila dalla home, inserisci la password (per esempio premendo Load KML e poi Annulla), correggi ora di partenza, TWD o lati e premi **Export for website**. Ricarica i due file su GitHub.

## Come vengono usati i log

Il log di un giorno contiene tutte le partenze di quel giorno: l'app le trova dal timer di regata. In ogni regata la tabella "Onboard start data" mostra le partenze di quel giorno ed evidenzia quella con l'ora più vicina (entro 10 minuti). Se l'ora di partenza della regata era solo stimata dalle tracce, viene sostituita con quella esatta del log.

## Daily report e database dei log di bordo

In home le regate sono raggruppate per giorno. Accanto alle regate di un giorno compare **Daily report** quando il database contiene il log di quel giorno.

**Caricare lo storico (una volta sola):**
1. Premi **Load history**, inserisci la password e scegli la cartella con tutti i log passati (.csv, solo tratti dritti).
2. L'app li legge (può volerci qualche minuto), li riduce a un valore al secondo e li divide per giorno. I dati non vengono filtrati: si usano così come sono.
3. Premi **Export for website** e carica su GitHub, nella cartella **data**, i file `history.json` e `logs.json`.

**Ogni giorno di regata:**
1. Premi **Load log** e scegli i .csv del giorno (già puliti: solo tratti dritti). L'app aggiunge il giorno al database così com'è, senza filtri. Se il log contiene anche il Race Timer, aggiorna pure la tabella delle partenze.
2. Premi **Export for website** e carica su GitHub `onboard.json`, `history.json` e `logs.json` (sostituiscono i vecchi).

`history.json` contiene tutto il database, quindi va ricaricato ogni volta. Un giorno pesa circa 300 KB. Se carichi di nuovo un giorno già presente, viene sostituito.

## Prima pubblicazione su GitHub Pages

1. Account su github.com (il nome utente entra nel link).
2. **New repository** → nome `race-analysis`, **Public** → **Create repository**.
3. **Add file → Upload files**: index.html e la cartella data → **Commit changes**.
4. **Settings → Pages** (se Settings non si vede, è nel menu "…") → Source: **Deploy from a branch** → **main** / **(root)** → **Save**.
5. Link: `https://NOMEUTENTE.github.io/race-analysis/`

## Da sapere

- La password blocca i pulsanti, ma in un sito statico il codice è leggibile. Quello che vedono gli altri cambia solo quando **tu** carichi i file su GitHub.
- Con un repository pubblico, i file delle regate sono scaricabili da chi conosce il link.

# Race Analysis · Phi!Number — come metterla online con il tuo nome

Il sito è fatto di 3 file e non ha bisogno di server o database:

```
index.html                         l'app
data/race.json                     la regata che vede chi apre il link
data/onboard.json                  la tabella "Onboard start data"
data/example-cartagena-r10.json    l'esempio (pulsante "Example")
```

Password per Load KML, Load log, Clear ed Export: **Phi-spinnaker-259**

---

## 1. Pubblicare su GitHub Pages (gratis)

L'indirizzo finale sarà **https://NOMEUTENTE.github.io/race-analysis/**, quindi scegli un nome utente con il tuo nome.

1. Crea un account su **github.com** (Sign up). Il nome utente diventerà parte del link, per esempio `mariorossi` darà `mariorossi.github.io`.
2. In alto a destra premi **+** e poi **New repository**.
   - Repository name: `race-analysis`
   - Visibilità: **Public** (con il piano gratuito Pages funziona solo con repository pubblici)
   - Premi **Create repository**.
3. Nella pagina del repository premi **uploading an existing file** (oppure **Add file → Upload files**).
   Trascina **index.html** e la **cartella data** (con i suoi file) così come sono nello zip. Premi **Commit changes**.
4. Vai su **Settings → Pages**.
   - Source: **Deploy from a branch**
   - Branch: **main**, cartella **/ (root)**, poi **Save**.
5. Dopo 1–2 minuti il sito è online su `https://NOMEUTENTE.github.io/race-analysis/`. Questo è il link da mandare al tuo amico.

## 2. Aggiornare la regata che vedono gli altri

1. Apri il tuo sito, premi **Load KML** e inserisci la password. Carica i KML della regata, e se vuoi anche i log con **Load log**.
2. Controlla ora di partenza, TWD e numero di lati.
3. Premi **Export for website**: scarica `race.json` (e `onboard.json` se hai caricato i log).
4. Su GitHub apri la cartella **data**, poi **Add file → Upload files**, trascina i file scaricati (sostituiscono quelli vecchi) e premi **Commit changes**.
5. Dopo circa 1 minuto chi apre il link vede la nuova regata.

## 3. Se vuoi usare il dominio phi-number.com

- **Sito già ospitato da un provider:** carica index.html e la cartella data in una cartella del sito, per esempio `/race-analysis/`, e il link sarà `phi-number.com/race-analysis/`.
- **Sottodominio con GitHub Pages:** in **Settings → Pages → Custom domain** scrivi per esempio `analysis.phi-number.com`, poi nel pannello DNS del dominio aggiungi un record **CNAME** `analysis` che punta a `NOMEUTENTE.github.io`.

## Da sapere

- La password blocca i pulsanti nella pagina, ma il codice di un sito statico è leggibile da chiunque. Anche chi la aggirasse caricherebbe file solo nel proprio browser: quello che vedono gli altri cambia solo quando **tu** carichi i file su GitHub.
- Con un repository pubblico, i file della regata (tracce GPS e dati di bordo) sono scaricabili da chiunque conosca il link.

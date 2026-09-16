# SENDit — rilasci

Qui ci sono **solo** l'elenco degli aggiornamenti e i pacchetti da installare.
**Nessun codice sorgente.**

## Per chi vuole solo il programma

Scarica l'ultima versione dalla cartella [`pacchetti/`](pacchetti/) e aprila.

**Windows dira' che ha protetto il PC**: succede a tutti i programmi che non
hanno un certificato comprato. Clicca su *Ulteriori informazioni* e poi su
*Esegui comunque*.

Si installa senza chiedere la password di amministratore, e mette il
collegamento nel menu Start. **Le sessioni gia' registrate non si toccano**:
stanno in una cartella loro, separata dal programma.

## Per noi — come funziona

`elenco.json` e' il file che il programma legge all'avvio per sapere se c'e'
una versione nuova. Dentro ci sono il numero dell'ultima versione, dove si
scarica, quanto pesa e la sua **impronta SHA-256** — che il programma
ricontrolla due volte: quando ha finito di scaricare, e di nuovo subito prima
di eseguire.

**Perche' i pacchetti stanno dentro il progetto e non fra gli «assets» del
rilascio**, che sarebbe il posto giusto: perche' l'host su cui GitHub vuole i
file dei rilasci (`uploads.github.com`) e' bloccato dalle regole di rete
dell'ambiente da cui pubblichiamo. `github.com` no, quindi i pacchetti
arrivano qui con un `git push` normale.

**Il prezzo di questa scelta:** la storia di git si tiene ogni versione per
sempre, anche quelle tolte. Ogni pacchetto pesa una quarantina di megabyte, e
nella cartella ne resta sempre e solo uno — ma il conto cresce lo stesso. Se un
giorno diventasse ingombrante, questo progetto si puo' **ricreare da zero senza
perdere niente**: non contiene codice, solo l'ultimo pacchetto e un file di
dieci righe.

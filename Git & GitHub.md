Git (che *forse* sta per Global information tracker) è un sistema di *version control* che permette ad un team di gestire un progetto arbitrariamente grande utilizzando una struttura ad albero per tenere conto degli aggiornamenti.
Github è la piattaforma più grande (stile social) che permette agli utenti di visionare progetti o *repositories* altrui.

Ci sono tanti comandi git ma i principali sono:

| comando                        | descrizione                                                                                                        |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| git clone \[url\]              | Scarica la repo corrispondente all'url nella directory corrente                                                    |
| git add \[file_name\]          | aggiunge il file selezionato (o tutti con .) allo "staging process"                                                |
| git commit -m "commit message" | "Salva" i cambiamenti correnti e li flagga col messaggio indicato                                                  |
| git push                       | invia i cambiamenti all'*origin*                                                                                   |
| git pull                       | scarica l'origin e confronta con la repo locale                                                                    |
| git merge                      | è forse il comando più importante, permette di gestire gli eventuali conflitti presenti nel codice appena pullato. |

----

Git è uno strumento potente per i team ma vanno seguite determinate linee guida.
1. Non lavorare contemporaneamente sullo stesso file. O in caso di necessità, non lavorare sulle stesse sezioni di codice.
2. prima di fare *qualunque* modifica, assicurarsi di essere al passo col branch corrente, attraverso un pull.
3. Fare *commit frequenti* e inviare i push a fine giornata / feature terminata.
4. Scrivere esaustivi messaggi di commit. Questo permette di ricondursi ad una specifica versione funzionante in caso di eventi catastrofici.
5. Evitare come la peste *git push --force*, spesso provoca danni e sofferenza.


### Solving conflicts 101

Capita il caso dove l'origin sia avanti di uno o più commit rispetto al ramo locale. In quel caso git bloccherà un tentato pull, a quel punto ci sono varie opzioni, si può mandare un commit con i cambiamenti locali, oppure usare il comando *git stash* per metterli da parte e ripristinarli (o scartarli) in seguito.
Se tutto fallisce **git reset --hard** come ultima spiaggia ripristinerà la repo all'ultimo commit trovato nell'origin, permettendo un successivo pull.


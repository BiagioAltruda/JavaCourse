https://www.w3schools.com/sql/

I database sono strutture ordinate di dati che vengono interrogati attraverso il linguaggio *SQL*. Le operazioni sui database sono di tipo *CRUD* (creation, reading, updating, deleting).

Il vantaggio principale dell'utilizzo di un database è la *persistenza* dei dati.
altri vantaggi sono: 
1. la capacità di immagazzinare grandi quantità di dati;
2. offrire funzionalità per gestione e sviluppo di applicazioni;
3. Garantire una buona velocità di elaborazione;
4. Consentire a più utenti di accedere ai dati;
5. Assicurare l'affidabilità dei dati.

La *Modellazione dei dati* è un processo di progettazione del database attraverso la creazione di *tables* (tabelle). Queste contengono dati contrassegnati da un *tipo* (intero, string boolean, etc). I dati sono salvati all'interno del Database per garantirne l'accesso anche tra esecuzioni diverse.

Ci sono 2 modelli principali:
1. Modello *Entità-Relazione*;
2. Modello a *Oggetti*.


#### Modello Entità-Relazione

Un'*entità* è qualsiasi cosa sul quale sono raccolte informazioni.
Gli *attributi* sono quegli oggetti che descrivono un'entità.
Le *Relazioni* sono oggetti che collegano le entità di un database.

Tutti gli oggetti devono avere nomi unici e significativi.

Il primo ci permette di usare entità (tabelle ad esempio) e relazioni, che sono i modi con cui le tabelle comunicano tra di loro, è quello che useremo principalmente.


I dati di due tabelle diverse potrebbero essere collegati attraverso delle relazioni. Un attributo di una tabella potrebbe essere segnato come *Primary Key*, una chiave che "indicizza" in maniera unica gli elementi di una tabella, come ad esempio il numero di matricola di studenti universitari.

Possiamo collegare due tabelle utilizzando una *Foreign Key*, che "punta" alla chiave primaria di un'altra tabella.


#### MySql
è un DbMs è un Database Managment System, che permette di interagire sia con i dati stessi che con i vari protocolli di sicurezza. 


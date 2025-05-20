è importante riuscire a leggere velocemente espressioni logiche, anche, complicate all'occorrenza, riporto i principali gate logici con le rispettive tabelle di verità

### AND &&
L'AND logico è vero se e solo se entrambe le entrate sono *vere*:

| A   | B   | A&B |
| --- | --- | --- |
| T   | T   | *T* |
| T   | F   | F   |
| F   | T   | F   |
| F   | F   | F   |
### OR ||
l'OR logico è vero se *almeno una* delle entrate è vera.

| A   | B   | A\|\|B |
| --- | --- | ------ |
| T   | T   | T      |
| T   | F   | T      |
| F   | T   | T      |
| F   | F   | *F*    |
### XOR
lo XOR è vero se e solo se le due condizioni *non* sono entrambe vere o false.

| A   | B   | A%B |
| --- | --- | --- |
| T   | T   | F   |
| T   | F   | *T* |
| F   | T   | *T* |
| F   | F   | F   |

------------
Questi sono tra gli operatori più importanti anche se ce ne sono altri. Notare che due operatori sono lo stesso operatore *se e solo se* le loro tabelle di verità corrispondono.
Da questa nozione scopriamo subito che negare (attraverso l'operatore !, NOT) un AND produce un OR e viceversa.

Per valutare la verità di un'espressione occorre passare prima dai rami innestati più profondi, fino a risalire all'inizio. Ad esempio:
```
x= 10;

x> 0 && (x<3 || x> 2) -->
--> x>0 && (true) -->
--> true && true --> true
oppure, più complicata

x=10;
 //dove in questo caso % indica l'operazione modulo
x<0 && (((x%3==0) || (x<15 && (x%2==0))) -->
--> x<0 && ((x%3==0) ||(true && true))-->
--> x<0 && (false || true) -->
--> false && true --> false
```

Per altri dettagli, consultare:
https://it.wikipedia.org/wiki/Algebra_di_Boole#XOR

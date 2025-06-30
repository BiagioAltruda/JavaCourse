HTML sta per *Hyper Text Markup Language* e NON è un linguaggio di programmazione.
HTML è lo standard per la creazione di pagine web.

```html
<!DOCTYPE html>
<html>

	<head>
		<title></title>
	<\head>
	
	<body>
		<h1>An Heading</h1>
		<p>a paragraph</p>
	</body>
</html>
```

Questa è la struttura base di un file HTML, la prima riga informa il browser che il file è un documento HTML. tra le parentesi angolari *<>* sono scritti i *tag* che dopo venire aperti spesso vanno anche chiusi con un */*. Un tag che di solito necessita di una chiusura, in caso di sua assenza, interagirà con tutto il resto del documento. 

In particolare il browser non compila la pagina ma la mostra così come viene definita, inclusi, se presenti, errori.

Tra i vari tag ci sono:

| Tag   | Descrizione                                                         |
| ----- | ------------------------------------------------------------------- |
| html  | contiene l'intero contenuto della pagina, questo tag è obbligatorio |
| head  | definisce la sezione dell'header                                    |
| title | permette di scrivere il titolo della pagina nel browser             |
| body  | corpo principale del documento                                      |
| h1    | grandezza standard maggiore per scrivere titoli di sezioni          |
| h...  | ...                                                                 |
| h6    | grandezza minore per scrivere titoli di sezioni                     |
| p     | scrittura di paragrafi                                              |
| br    | manda a capo. Non ha bisogno di essere chiuso                       |
| a     | Si usa per creare dei *link*                                        |

### tag \<a>
Il tag *\<a>\</a>* permette di creare dei collegamenti ipertestuali, ad esempio:
```html
...
<a href= "https://google.com"> Google </a>
...
```
è un link cliccabile che reindirizza alla pagina di google.com.
*href* è un *attributo* che ha lo scopo di specificare le caratteristiche di quello specifico tag.
l'attributo *target* cambia in quale pagina aprire il collegamento. Ad esempio *target =_blank* aprirà il link in una nuova scheda.


### tag \<img>

Usato per caricare delle immagini nella pagina:
```html
...

<img src ="percorso\della\immagine.jpg" width = "250" height ="40">
<img alt = "Testo alternativo">
...
```

*src* indica il percorso da seguire per trovare l'immagine da caricare, mentre *alt* propone un'alternativa testuale nel caso l'immagine non venga caricata.
*width* e *height* specificano larghezza e altezza dell'immagine.
*img* non necessita di un tag di chiusura
# CSS
Tutta la parte grafica come colore, font, etc, viene gestito da un file *.css*.
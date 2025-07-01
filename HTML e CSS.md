HTML sta per *Hyper Text Markup Language* e NON è un linguaggio di programmazione.
HTML è lo standard per la creazione di pagine web.

```html
<!DOCTYPE html>
<html>

	<head>
		<title></title>
	</head>
	
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
*img* non necessita di un tag di chiusura.

## Form
I form sono dei moduli che permettono all'utente di inviare dati al server.
```html
...

<body>
	<form action= "/action_page.php">
		<label for= "fname">First name: </label><br>
		<input type= "text" id="fname" name="fname" values="John"><br>
		<label for= "lname">Last name: </label><br>
		<input type= "text" id="lname" name="lname" values="Doe"><br><br>
		<input type= "submit" value="Submit">
	</form>
</body>
...
```

L'attributo *label* indica il nome del campo da compilare.
L'attributo *input* specifica i dettagli dell'input da inserire, in particolare *text* è una stringa e il tipo *submit* si crea un pulsante per l'invio dei dati del form.
L'attributo *action* indica in quale pagina i dati inseriti vanno inviati.
Tecnicamente *value* è incorretto, è consigliabile utilizzare al suo posto *placeholder* che piazza nel form una scritta sovrascrivibile.
Al form posso aggiungere l'attributo *method*:
```html
...
<form action="/action_page.php" method="POST">
</form>
...
```
che può prendere come valori: *GET, POST, PUT, DELETE*. Lo standard è GET.


Ci sono vari tipi di *input*:

| Type                            | Descrizione                                                                                                        |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `<input type="text">`           | Testo normale per informazioni brevi                                                                               |
| `<input type="password">`       | Testo censurato per inserimento di passwords                                                                       |
| `<input type="Submit">`         | Pulsante di invio dati                                                                                             |
| `<input type="radio">`          | Scelta singola tra vari valori predefiniti                                                                         |
| `<input type="checklist">`      | Scelta multipla tra vari valori predefiniti                                                                        |
| `<input type="date">`           | Form specifico per inserire delle date, includendo gli attributi min e max per limitare il lasso di tempo inserito |
| `<input type="datetime-local">` | Aggiunge all'opzione precedente un orario                                                                          |
| `<input type="email">`          |                                                                                                                    |
| `<input type="file">`           | Apre una finestra per caricare un file da locale                                                                   |
| `<input type="number">`         | Inserimento di un numero, includendo min e max possiamo dare dei bound all'input                                   |
| `<input type="range">`          | Crea uno slider, necessita di min e max                                                                            |
| `<input type="search">`         | Esattamente come text, su alcuni browsers cambia la visualizzazione                                                |
| `<input type="phone">`          | Inserimento di un numero di telefono                                                                               |
| `<input type="time">`           | Inserimento di un orario                                                                                           |
| `<input type="url">`            | Inserimento di url di un sito                                                                                      |

In input altri attributi importanti sono:
1. *readonly* che inserisce un valore non modificabile,
2. *size* fissa graficamente la dimensione del campo ma non la quella del dato in sé,
3. *maxlength* specifica quanti caratteri possono essere inseriti,
4. *required* obbliga l'utente a compilare il campo,

Il tag *select* permette crea un menù a tendina per scegliere delle opzioni:
```html
<form action="/action_page.php">
	<label for="cars">Choose a car:</label>
	<select id="cars" name="cars">
		<option value="volvo">Volvo</option>
		<option value="saab">Saab</option>
		<option value="fiat">Fiat</option>
		<option value="audi">Audi</option>
	</select>
	<input type="submit">
</form>
```

![image](Pasted image 20250701111724.png)

Ne è consigliato l'utilizzo quando ci sono molte opzioni tra cui scegliere.

L'attributo *multiple* in select permette di scegliere più opzioni tenendo premuto Ctrl su Windows o Command su Mac (non si usa praticamente più).

Il tag *textarea* si utilizza per inserire molto testo:
```html
...
<form action="/action_page.php" method="POST">
	<textarea name="message" rows="10" cols="30">Some placeholder text. </textarea><br><br>
	<input type="submit">
</form>

<form action="/action_page.php" method="POST">
	<textarea name="message" rows="10" cols="30" placeholder="Some placeholder text"></textarea><br><br>
	<input type="submit">
</form>
...
```


![[Pasted image 20250701111841.png]]

La seconda opzione è preferibile.

Il tag *fieldset* "incapsula" il form e separare graficamente pezzi del form:

```html
<form action="/action_page.php">
	<fieldset>
		<legend>Dati personali</legend>
		<label for= "fname">First name: </label><br>
		<input type= "text" id="fname" name="fname" values="John"><br>
		<label for= "lname">Last name: </label><br>
		<input type= "text" id="lname" name="lname" values="Doe"><br><br>
	</fieldset>
	<fieldset>
		<legend>Dati pagamento></legend>
		<label for= "fname">Nome sulla carta</label><br>
		<input type= "text" id="fname" name="fname"><br>
		<label for= "cardnumber">Card number</label><br>
		<input type= "number" id="cardnumber" name="cardnumber"><br><br>
	</fieldset>
	<input type= "submit" value="Submit">
</form>
```

![[Pasted image 20250701111929.png]]

# CSS
Tutta la parte grafica come colore, font, etc, viene gestito da un file *.css*.

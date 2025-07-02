Uno dei due principali modi con cui faremo il *deployment* delle nostre webapps sarà attraverso questa struttura, con (quasi) sempre lo stesso scheletro e setup di base.

## Creazione progetto

Dopo essersi assicurati di aver installato correttamente il server **Apache Tomcat V10.1** attraverso i *Java EE* tools procediamo con *Maven*, il build manager del progetto.

1. Creare un nuovo progetto di eclipse e scegliere tra le opzioni *Maven Project*.
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Progetto1.png)
2. Premere *Next* e poi spuntare *Create a simple project (skip archetype selection)*.
	![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Progetto2.png)
3. Premere su *Next* e poi compilare i campi *Group Id*, *Artifact Id* e modificare *Packaging* da *jar* a *war*.
	![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Progetto3.png)

# Configurazione generale
Una volta finito otterremo un progetto fatto in questa maniera:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf1.png)

Come prima cosa adesso, facciamo il *deploy* del progetto *Vendite* sul nostro server.
Tasto destro sul server, poi *Add and Remove*:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf2.png)

Selezionare il progetto.

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf3.png)

e aggiungerlo premendo *add* come mostrato.

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf4.png)

Abbiamo aggiunto la webapp al server locale di Tomcat.

Ora andiamo sul file *pom.xml* che contiene la configurazione di Maven, installeremo qui le dependencies necessarie.

Assicurarsi che il file rispecchi:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf5.png)

Successivamente inserire subito sotto il tag *packaging* le seguenti istruzioni:
```xml
<dependencies>
	<dependency>
		<groupId>jakarta.servlet</groupId>
		<artifactId>jakarta.servlet-api</artifactId>
		<version>6.0.0</version>
		<scope>provided</scope>
	</dependency>
	<dependency>
		<groupId>mysql</groupId>
		<artifactId>mysql-connector-java</artifactId>
		<version>8.0.33</version>
	</dependency>
</dependencies>
```

come in figura:

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/PomXML.png)



Salvare il *pom.xml*. 

Potrebbe essere che il file *web.xml*, non sia presente.

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/WebXML1.png)
![[WebXML1.png]]
In questo caso, fare tasto destro sul progetto e poi *Generate Deployment Descriptor Stub*:
![[WebStub.png]]

Aprire il file e cancellare tutti i tag *servlet*, *servlet-mapping* e i loro contenuti.
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/WebXML2.png)

Quando si crea un nuovo servlet accertarsi che maven aggiunga di nuovo questi tag.

Tasto destro sul file poi seguire la figura:

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf6.png)

Appena premuto *Maven install*, maven si occuperà di installare tutte le dependencies che abbiamo specificato nel file di configurazione.
Questo dovrebbe essere il risultato in console.
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf7.png)

Per controllare se effettivamente funziona tutto correttamente creiamo un *Servlet*, un intermediario tra il progetto e il server in sé, sarà il *main* del nostro progetto.

![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf8.png)

Una volta premuto su Servlet, compilare il wizard:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Servlet1.png)

Per qualche motivo, questa versione di eclipse importa, di default, delle librerie errate. Quindi cancellare questi import:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf10.png)

e poi premere `Ctr+Shift+o` sulla tastiera per importare automaticamente tutte le librerie richieste.
Se lo shortcut non funziona o siete su mac/linux, tasto destro dentro il file e poi premere *Organize imports* come in foto:
![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Conf9.png)

A questo punto la configurazione in sé del progetto è finita e si può iniziare a lavorare.

# Funzionamento Servlet e buone pratiche

Il servlet ha in partenza *3* componenti principali:

1. `@WebServlet("/TestSrv")`, questa annotazione manda in esecuzione il servlet quando la stringa tra virgolette (tipicamente il nome del servlet) appare nell'URL della pagina.
2. Il metodo `doGet`, questo è il metodo principale in cui inserire la logica dell'applicazione, sarà virtualmente il nostro main.
3. Il metodo `doPost`, who knows \?\_\?.


![not found](https://github.com/BiagioAltruda/JavaCourse/blob/main/Servlet2.png)

Fatto questo, iniziamo a strutturare i vari package che costituiranno il progetto.
Oltre al package *com* avremo bisogno di creare:
1. *ctr*, metteremo qui i vari Servlet che gestiranno la nostra applicazione.
2. *dao*, sta per *Data Access Object*, qui dentro bisognerà creare una nuova classe per ogni tabella del nostro *database*.
3. *model*, andrà a contenere il resto dei costrutti principali, come ad esempio le classi instanziabili.


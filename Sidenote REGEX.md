Questo non è veramente fondamentale per lo scopo del corso, ma saperlo, secondo me, è bene. Avventuratevi a vostro pericolo.
Il REGEX è il linguaggio delle espressioni regolari, non entrando nella definizione specifica, sono delle espressioni, pattern, che permettono di isolare determinati pezzi di testo.

la sintassi è "modulare", nel senso che i vari blocchi possono essere modificati dai vari operatori.
un blocco si identifica con le parentesi quadre \[]. Ad esempio se vogliamo trovare tutte le vocali nella parola "aiuola", useremo il blocco *\[aeiouAEIOU]*. Come si vede per indicare lettere o numeri singoli basta scriverli uno dopo l'altro tra le quadre. 
Se vogliamo dare un range di lettere o numeri si usano i dash *-*. Ad esempio \[a-zA-Z] descrive tutte le lettere dalla a alla z prima minuscole e poi maiuscole, così come \[0-9] descrive tutte le cifre da 0 a 9.

Un *Capturing Group* si indica con le parentesi tonde (). Si usa per modificare interi pezzi di sintassi. Ad esempio scrivere un numero *n* in parentesi graffe dopo un  un capturing group, richiederà che il testo rispetti il gruppo con *n* caratteri di fila. Ad esempio: (\[aei]){*3*} nella stringa aeiou troverà come match: aei. Se invece fosse stato  (\[aei]){*2*} nella stessa stringa, riconoscerebbe solo: ae.

Segue una tabella con i token più comuni:

| descrizione                           | sintassi |
| ------------------------------------- | -------- |
| Carattere singolo tra a, b, c         | \[abc]   |
| Qualunque carattere tranne a, b, c    | \[^abc]  |
| Ogni carattere alfabetico tra a e z   | \[a-z]   |
| Ogni carattere fuori il range a, z    | \[^a-z]  |
| Qualunque caratteri singolo           | .        |
| Matcha indistintamente a o b          | a\|b     |
| Qualunque carattere di whitespace     | \s       |
| Qualunque carattere non di whitespace | \S       |
| Qualunque cifra                       | \d       |
| Qualunque non cifra                   | \D       |
| Qualunque parola                      | \w       |
| Qualunque non parola                  | \W       |
| Non un capturing group                | (?:...)  |
| Capturing group                       | (...)    |
| Zero o uno di a                       | a?       |
| Zero o più di a                       | a*       |
| Uno o più di a                        | a+       |
| Esattamente n di a (n è un numero)    | a{n}     |
| n o più di a                          | a{n,}    |
| Inizio di una stringa                 | ^        |
| Fine di una stringa                   | $        |
In generale ci sono molti altri token, ma questi sono i più comuni e quelli più importanti da saper maneggiare.
sul sito https://regex101.com/ si può testare, usare e consultare la documentazione.

Se ho tempo/voglia inserirò degli esempi un po' più complicati, se non ci sono **don't @ me**, i'm already insane.

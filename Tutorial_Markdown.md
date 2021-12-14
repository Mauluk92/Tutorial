# 1 Markdown per Github #

Markdown è un linguaggio di markup (affine al HTML) per creare testi formattati mediante editor testuali (questo documento è stato creato attraverso un blocco note sfruttando
markdown)
Di seguito viene illustrata la sintassi fondamentale.

## 1.1 Intestazioni 

Le intestazioni (come quella di sopra) si dividono in 6 livelli (per chi conosce l'HTML, sono equivalenti ai tag `<h1>,<h2>`..ecc..).
Esempio:
```
# Intestazione livello 1 

## Intestazione livello 2 

### Intestazione livello 3 

#### Intestazione livello 4 

##### Intestazione livello 5 

###### Intestazione livello 6 
```
La cui resa finale è la seguente (ricordarsi di lasciare sempre uno spazio dopo i cancelletti):
# Intestazione livello 1 

## Intestazione livello 2 

### Intestazione livello 3 

#### Intestazione livello 4 

##### Intestazione livello 5 

###### Intestazione livello 6 

## 1.2 Paragrafi 

I paragrafi vengono separati come in un qualunque editor di testo normale (come word): infatti a differenza dell'HTML non è necessario introdurre alcun elemento per separare due paragrafi, solo una riga vuota.  

Come in questo caso.

## 1.3 Punto e a capo 

Per andare a capo occorre lasciare due spazi(o più) dopo il punto finale.  

## 1.4 Enfasi 

### 1.4.1 Grassetto

Per il grassetto occorre circondare la frase o la parola da enfatizzare con due asterischi consecutivi. Esempio:  
```
**frase in grassetto**
```
La cui resa è la seguente: **frase in grassetto**. Ciò equivale ai tag HTML `<strong>`.

### 1.4.2 Italic 

Se si utilizza un solo asterisco l'effetto è il seguente: *frase enfatizzata*, simile all'effetto ottenuto mediante il tag HTML `<em>`.

### 1.4.3 Entrambe 

Infine se si vogliono utilizzare entrambi gli effetti si usano ***tre asterischi***.

## 1.5 Liste

### 1.5.1 Liste ordinate 

Per creare liste ordinate si mette all'inizio di ogni riga `1.` seguito da uno spazio (oppure `2.` e così via..). Esempio:
```
1. Primo elemento ordinato 
2. Secondo elemento ordinato 
3. Terzo elemento ordinato
```
Il cui effetto è il seguente:
1. Primo elemento 
2. Secondo elemento 
3. Terzo elemento

### 1.5.2 Liste non ordinate ###

Le liste non ordinate funzionano in modo esattamente analogo, ma utilizzano gli asterischi a inizio riga, come in questo esempio:
```
* Primo elemento non ordinato 
* Secondo elemento non ordinato 
* Terzo elemento non ordinato 
```
L'effetto risultante è questo:
* Primo elemento non ordinato
* Secondo elemento non ordinato 
* Terzo elemento non ordinato 

## 1.6 Blocchi di codice 

Per creare blocchi di codice, ovvero sezioni del testo evidenziate, si usano i backtick \`: su Windows possono essere creati con la combinazione **ALT + 96**.
In generale un solo backtick serve per creare codice *in-line* ovvero su di una riga di testo come per esempio \`questo frammento\` che è reso così: `questo frammento`.
Tuttavia si possono usare anche tre backtick: in tal caso il codice si estenderà per più riga (un po' come i tre apostrofi per Python! Per creare stringhe multiriga!).
```
Questo è un esempio
di 
codice 
multiriga
```
### 1.6 Blocchi di codice: evidenziatori di sintassi 
Markdown permette di evidenziare la sintassi (come in un IDE!) dei linguaggi che si vogliono incorporare all'interno del testo in markdown.
Per farlo è sufficiente usare i tre backtick e digitare subito dopo il nome del linguaggio. Esempio:
\`\`\`python
codice in python multi riga  
\`\`\`
 
## 1.5 Link

Markdown può incorporare i link al suo interno (sia relativi al repository di Github, che esterni!):
Esempio:
```
[NOME DEL LINK](https:\\www.google.it)
```
La cui resa effettiva è la seguente:
[NOME DEL LINK](https:\\www.google.it)

Se al posto dell'url di un sito inseriamo il percorso delle directory di github otteniamo lo stesso risultato.
Questo può tornare utile nel caso in cui si voglia inserire una immagine all'interno del README.md del repository.
La sintassi tuttavia è leggermente diversa:
```
![NOME DEL COLLEGAMENTO](path/to/my/folder/image/photo.png)
```
E' richiesto un punto esclamativo.

I link poi possono tornare utili per riferirsi a *parti dello stesso documento markdown*.
Per esempio, con la seguente sintassi mi riferisco al primo capitolo di questo documento:
```
[Primo capitolo](#intestazione-livello-1)
```
La cui resa è la seguente:
[Primo Capitolo](#intestazione-livello-1)

Markdown "sa" a quale parte del documento ci riferiamo. Cerca tra le intestazioni quelle che corrispondono alla frase dopo il cancelletto, eliminando i trattini, convertendo tutto in lowercase ed eliminando gli spazi prima e dopo l'intestazione stessa.

Questo può essere sfruttato per creare delle **TOC** (Table of Contents), degli indici per la consultazione del nostro documento.

ENJOY :)




 



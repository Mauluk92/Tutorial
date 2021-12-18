# Come effettuare il deploy di un applicativo su Heroku

## 1.1 Aprire la git bash e creare un ambiente virtuale

Per creare un ambiente virtuale nella cartella del progetto da caricare su heroku è sufficiente installare virtualenv da gitbash come segue:
```bash 
$ pip install virtualenv
```
Dopodiché usare l'applicazione virtualenv per creare l'ambiente virtuale all'interno della cartella progetto:
```bash 
$ virtualenv env
```
Da notare che `env` può avere qualunque nome,  è semplicemente il nome della cartella che andrà a contenere il nostro ambiente.

## 1.2 Attivazione ambiente virtuale 

Per attivare l'ambiente virtuale da Git Bash dobbiamo digitare:
```bash 
$ source env/Scripts/activate
```
Dovrebbe a questo punto apparire un `(env)` sopra la riga di comando per confermare che ci troviamo in un ambiente virtuale.

## 1.3 Installazione flask e gunicorn

A questo punto procediamo a installare flask e gunicorn con i seguenti comandi:
```bash 
$ pip install flask gunicorn
```
Possiamo procedere con la creazione dell'applicativo vero e proprio.

## 1.4 Creazione dell'applicazione principale

L'applicazione principale andrebbe creata nella cartella del progetto. Nel mio caso ho scelto il nome `white_rose.py`, ma è irrilevante quale nome scegliate.
L'applicativo deve avere questa forma:
```python
from flask import Flask

nome_applicativo = Flask(__name__) # Va bene qualunque nome ma una volta scelto, occorre riusarlo in tutto lo script

@nome_applicativo.route('/')       # Si tratta di un decoratore: una struttura sintattica che permette di modificare la funzione sottostante in modo da farla interagire con Flask
def index():
	return '<h1> Ciao Mondo! </h1>' # Di nuovo il nome della funzione index è del tutto arbitrario. Ho scelto index perché il decoratore crea la funzione associata alla pagina principale ('/')

if __name__ == '__main__':
	nome_applicativo.run(debug=True)
```

Ora che abbiamo creato il nostro applicativo nella cartella principale del progetto procediamo con gli altri due file.

## 1.5 Creazione del requirements.txt

Per creare i requirements.txt semplicemente facciamo:
```bash
$ pip freeze > requirements.txt
```

Dalla git bash.

## 1.6 Creazione del Procfile (file dei processi) 

Per avviare il nostro applicativo dobbiamo specificare il processo principale nel nostro Procfile (Process File):
Creiamo quindi un documento privo di estensioni (non .txt) all'interno della cartella principale. Nel mio caso avrà la seguente forma:
```
web: gunicorn white_rose:nome_applicativo
```
La sintassi per l'ultima parte del file è il seguente:
```
nome_file_python_senza_estensione:nome_applicativo_nel_file_python
```
## 1.7 Connessione a heroku 

Digitiamo sulla bash `heroku login` e dopo aver effettuato il login, uscire dalla schermata con CTRL + C.
Ora che siamo connessi possiamo creare il nostro applicativo.

## 1.8 Creazione e deploy 

Scrivere sulla gitbash
```bash 
heroku creare nome_progetto
```
Dopodiché, una volta creato, inizializziamo il nostro repository
```bash
git init
```
Ora colleghiamo il nostro repository a quello di heroku:
```bash
heroku git:remote -a nome_progetto
```
Aggiungiamo i file della cartella principale con il comando:
```bash
git add Procfile requirements.txt file.py
```
Il file.py è ovviamente il file python che contiene l'applicazione del progetto che abbiamo creato noi (nel mio caso, white\_rose.py).
Infini committiamo e poi pushiamo il tutto sulla master branch del repository:
```bash
git commit -m "Commento sul commit"
git push heroku master
```
Una volta finito, possiamo consultare il nostro applicativo sulla relativa pagina web di Heroku!
Enjoy.


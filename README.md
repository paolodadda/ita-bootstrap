# Linee guida di design per i siti web della Pubblica Amministrazione
## Implementazione CSS/HTML di riferimento

L'implementazione di riferimento contiene un CSS riutilizzabile basato sulla versione 3.3.5 del framework [Bootstrap](https://github.com/twbs/bootstrap-sass).

### Contenuto

* `dist/css/ita-bootstrap.css`: file CSS riutilizzabile basato su Bootstrap
* `dist/js/`: file Javascript Bootstrap e jQuery
* `dist/*.html`: file html esemplificativi

### Installazione dell'ambiente di sviluppo

La procedura di seguito descritta è rivolta a chi vuole contribuire allo sviluppo del tema / CSS
e non è necessaria per utilizzare il CSS (`dist/ita-bootstrap.css`) all'interno di un sito web.

La personalizzazione del CSS si basa su alcuni prerequisiti:

* [node e npm](https://nodejs.org)
* [Bower](http://bower.io)
* [Gulp](http://gulpjs.com/)

Dopo aver installato nodejs e npm, 
è possibile effettuare un nuovo build eseguire questi comandi:

````
> npm install -g bower gulp
> npm install
> bower install
> gulp dist
````

### Struttura file-system

Il file system è così organizzato:

```
ita-bootstrap/
│
├── sass/
│   ├── ita-bootstrap.scss
│   ├── _custom.scss
│   └── bootstrap/
│          ├── _variables.scss
├── html/
│   ├── index.html
│   ├── bottoni.html
│   ├── ...
│
├── dist/
│   ├── index.html
│   ├── bottoni.html
│   ├── ...
│   │
│   ├── css/
│   │    └── ita-bootstrap.css
│   │
│   ├── fonts/
│   │    ├── ...
│   │
│   └── js/
│        ├── bootstrap.min.js
│        ├── ...
```

Le variabili personalizzate di Bootstrap e le regole specifiche per le linee guida sono contenute nei due file *partial*:

* `bootstrap/_variables.scss`: modifica le variabili standard di Bootstrap e sovrascrive le impostazioni di Bootstrap
* `_custom.scss`: incluso in cascata a Bootstrap, modifica le regole Bootstrap

Il comando:
````
> gulp dist
````
provvede a rigenerare la cartella `dist` rispecchiando le modifiche effettuate.

Durante lo sviluppo, è possibile utilizzare il comando:
````
> gulp watch
````
per mantenere allineato il file-system `dist` ad ogni salvataggio dei file `html` e `scss`.

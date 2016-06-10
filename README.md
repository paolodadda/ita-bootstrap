# Implementazione CSS/HTML Linee guida di design per i siti web della Pubblica Amministrazione

Implementazione delle linee guida con un CSS Bootstrap-based.
L'implementazione è basata su [Bootstrap-sass](https://github.com/twbs/bootstrap-sass) v.3.3.5.

## Quick start

La cartella `dist` contiene il quanto serve per creare un website utilizzando il css che implementa le linee guida:

* `dist/css/agid.css`: file CSS Bootstrap-based.
* `dist/js/`: file Javascript Bootstrap e jQuery
* `dist/fonts/`: file fonts usati da Bootstrap
* `dist/*.html`: file html esemplificativi

## Installazione

La personalizzazione del CSS si basa su alcuni prerequisiti:

* [node e npm](http://nodejs.org/).
* [Bower](http://bower.io).
* [Gulp](http://gulpjs.com/).

Dopo aver installato nodejs ed npm, è sufficiente eseguire questi comandi:

````
> npm install -g bower gulp
> npm install
> bower install
> gulp dist
````

### Struttura file-system

Il file system è così organizzato:

```
agid-guidelines/
│
├── sass/
│   ├── agid.scss
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
│   │    └── agid.css
│   │
│   ├── fonts/
│   │    ├── ...
│   │
│   └── js/
│        ├── bootstrap.min.js
│        ├── ...
```

Le regole personalizzazioni di Bootstrap e le regole specifiche per le Linee guida sono contenute nei due file *partial*:
* `bootstrap/_variables.scss`: modifica le variabili standard di Bootstrap e sovrascrive le impostazioni di Bootstrap
* `_custom.scss`: incluso in cascata a Bootstrap, modifica le regole Bootstrap.

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

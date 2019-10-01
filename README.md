# Installazione e configurazione

## Linux

Installare nteract (da appimage). Le istruzioni qui di seguito installano tutte le dipendenze in virtual environment isolati.

### Python

Pre-requisiti:

- Installare Python3 e pip
- Installare pipenv (globally): `sudo pip install pipenv`

Installazione:

- Creare cartella di progetto sul disco: `mkdir my-project && cd my-project/`
- Attivare il virtualenv: `pipenv --three shell`
- Installare il kernel: `pipenv install ipykernel`
- Lanciare il kernel: `python -m ipykernel install --user`
- Installare eventuali dipendenze del proprio progetto: `pipenv install [dependencies]`

### R

Pre-requisiti:

- Installare R
- Installare packrat (globally): `sudo R -e 'install.packages("packrat")'`
- Installare le librerie necessarie: `sudo apt install libssl-dev libxml2-dev`

Installazione:

- Creare cartella di progetto sul disco: `mkdir my-project && cd my-project/`
- Attivare il virtualenv: `R -e packrat::init()`
- Installare le dipendenze del kernel (R shell): `install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))`
- Installare il kernel: `devtools::install_github('IRkernel/IRkernel')`
- Lanciare il kernel: `IRkernel::installspec()`
- Sostituire il comando in ~/.local/share/jupyter/kernels/ir/kernel.json con `packrat::init(\"my_project_abs_path\"); IRkernel::main()`
- Installare eventuali dipendenze del proprio progetto (R shell): `install.packages(c([dependencies]))`

### Javascript

Pre-requisiti:

- Installare nodejs e npm

Installazione:

- Creare cartella di progetto sul disco: `mkdir my-project && cd my-project/`
- Inizializzare il progetto: `npm init`
- Installare il kernel: `npm install ijavascript --save`
- Lanciare il kernel: `npx ijsinstall`
- Sostituire il comando in ~/.local/share/jupyter/kernels/javascript/kernel.json con `my_project_abs_path/node_modules/.bin/ijskernel`
- Aggiungere l'opzione `--session-working-dir=my_project_abs_path` in ~/.local/share/jupyter/kernels/javascript/kernel.json
- Installare eventuali dipendenze del proprio progetto: `npm install [dependencies] --save`

## Windows

Installare nteract (dall'installer exe). Le istruzioni qui di seguito installano tutte le dipendenze globalmente per l'utente corrente.

### Python

Pre-requisiti:

- Installare Python 3

Installazione:

- Installare il kernel (Powershell): `pip3 install ipykernel`
- Attivare il kernel: `py -3 -m ipykernel install`

### R

Pre-requisiti:

- Installare R

Installazione:

- Installare le dipendenze (da R Gui): `install.packages(c('repr', 'IRdisplay', 'evaluate', 'crayon', 'pbdZMQ', 'devtools', 'uuid', 'digest'))`
- Installare il kernel (da R Gui): `devtools::install_github('IRkernel/IRkernel')`
- Attivare il kernel (da R Gui): `IRkernel::installspec()`

### Javascript

Il kernel per javascript è built-in.

## MacOS

WIP

### Python

### R

### Javascript

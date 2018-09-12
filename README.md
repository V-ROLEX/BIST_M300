# BIST_M300 | L.Widmer
## Bash

Bash (für Bourne-again shell)) ist eine freie Unix-Shell und Teil des GNU-Projekts. Sie ist heute auf vielen unixoiden Systemen die Standard-Shell.
Bash wird Verwendet zur Ausführung von Shellscripts und zum Einloggen (via ssh) auf die Virtuellen Maschinen.
Ist bei Mac direkt installiert

## GIT

Git ist eine freie Software zur verteilten Versionsverwaltung von Dateien, die durch Linus Torvalds initiiert wurde.
Git wird Verwendet als Client zu Versionsverwaltungssystemen.
Ist bei Mac direkt installiert

### Command line instructions

```shell
Git global setup<br>
git config --global user.name "V-ROLEX"<br>
git config --global user.email "lorisw99@hotmail.com"<br>
```
### Create a new repository

```shell
cd Schule/BIST_M300/BIST_M300<br>
git clone https://github.com/V-ROLEX/BIST_M300.git<br>
touch README.md<br>
git add README.md<br>
git commit -m "Text bei Commit"<br>
git push<br>
```
### Existing folder

```shell
cd existing_folder<br>
git init<br>
git remote add origin https://github.com/V-ROLEX/BIST_M300.git<br>
git add .<br>
git commit -m "Initial commit"<br>
git push -u origin master<br>
```
### Existing Git repository

```shell
cd existing_repo<br>
git remote rename origin old-origin<br>
git remote add origin git@gitlab.com:robin.augstburger/M300.git<br>
git push -u origin --all<br>
git push -u origin --tags<br>
```
## GitHub

## VirtualBox

VirtualBox ist eine Virtualisierungssoftware und erlaubt es, lokal auf dem PC sogenannte Virtuelle Maschinen zu Erstellen und zu Verwalten.
VirtualBox wird verwendet weil das Zusammenspiel mit vagrant am Besten funktioniert und die Software frei Verfügbar ist (Open Sourcen).
VirtualBox ab Webseite

## Vagrant

Vagrant ist eine Open-Source Ruby-Anwendung zum Erstellen und Verwalten von virtuellen Maschinen, mittels sogenannten Vagrantfiles.
Vagrant ab Webseite 

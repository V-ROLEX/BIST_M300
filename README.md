# BIST M300 | L.Widmer
## Bash

Bash (für Bourne-again shell)) ist eine freie Unix-Shell und Teil des GNU-Projekts. Sie ist heute auf vielen unixoiden Systemen die Standard-Shell.
Bash wird Verwendet zur Ausführung von Shellscripts und zum Einloggen (via ssh) auf die Virtuellen Maschinen.

## GIT

Git ist eine freie Software zur verteilten Versionsverwaltung von Dateien, die durch Linus Torvalds initiiert wurde.
Git wird Verwendet als Client zu Versionsverwaltungssystemen.

### Command line instructions

```shell
git global setup
git config --global user.name "V-ROLEX"
git config --global user.email "lorisw99@hotmail.com"
```
### Create a new repository

```shell
cd Schule/BIST_M300/BIST_M300
git clone https://github.com/V-ROLEX/BIST_M300.git
touch README.md
git add README.md
git commit -m "Text bei Commit"
git push
```
### Existing folder

```shell
cd existing_folder
git init
git remote add origin https://github.com/V-ROLEX/BIST_M300.git
git add 
git commit -m "Initial commit"
git push -u origin master
```
### Existing Git repository

```shell
cd existing_repo
git remote rename origin old-origin
git remote add origin git@gitlab.com:robin.augstburger/M300.git
git push -u origin --all
git push -u origin --tags
```
## GitHub

## VirtualBox

VirtualBox ist eine Virtualisierungssoftware und erlaubt es, lokal auf dem PC sogenannte Virtuelle Maschinen zu Erstellen und zu Verwalten.
VirtualBox wird verwendet weil das Zusammenspiel mit vagrant am Besten funktioniert und die Software frei Verfügbar ist (Open Sourcen).

## Vagrant

Vagrant ist eine Open-Source Ruby-Anwendung zum Erstellen und Verwalten von virtuellen Maschinen, mittels sogenannten Vagrantfiles.

## Markdown

Markdown ist eine vereinfachte Auszeichnungssprache, die von John Gruber und Aaron Swartz entworfen und im Dezember 2004 mit Version 1.0.1 spezifiziert wurde. Ein Ziel von Markdown ist, dass schon die Ausgangsform ohne weitere Konvertierung leicht lesbar ist. Als Auszeichnungselemente wurden daher vor allem Auszeichnungsarten verwendet, die in Plain text und E-Mails üblich sind. Auch andere Auszeichnungssprachen mit ähnlichen Zielen zur Lesbarkeit – wie reStructuredText oder Textile – hatten Einfluss auf die Syntax.

[Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
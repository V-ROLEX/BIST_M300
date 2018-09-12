#Ubunut Server VM einrichten | L.Widmer
## Vagrantfile erstellen
```shell
1. mkdir Ordnername
2. cd Ordnername
3. vagrant init ubuntu/trusty64
4. vagrant up --provider virtualbox
5. vagrant ssh
```
## Portweiterleitung einrichten
1. VirtualBox öffnen 
2. Auf den Reiter Ändern
3. Unter Netzwerk auf erweiterte Einstellungen
4. Und Angaben wie im Bild anpassen
   
![Portweiterleitung](/Bilder/Portweiterleitung.png)

## Apache installieren
Der Apache HTTP Server ist ein quelloffenes und freies Produkt der Apache Software Foundation und der meistbenutzte Webserver im Internet.

Der Apache-Server kann sehr gut mit sogenannten Modulen erweitert werden, die bestimmte Zusatzfunktionen mitbringen und immer mit 'mod_' beginnen (z. B. mod_rewrite, mod_php5, mod_ssl).

Es gibt Module u. a. für

..*SSL (mod_ssl für OpenSSL, mod_gnutls für GnuTLS)
..*Einbindung und Verwendung von dynamischen Skriptsprachen (u. a. mod_php5, mod_perl, mod_python)
..*Unterstützung von zusätzlichen Protokollen (WebDAV: mod_dav, mod_dav_fs, mod_dav_lock, mod_dav_repos)
..*Authentifizierung (mod_auth*)
..*Weiterleitung an andere Server (mod_proxy)

```shell
sudo apt-get install apache2 apache2-doc 
sudo a2enmod cgi
sudo service apache2 restart
```

## Nützliche Befehle
### Bash
#### Administrator, Start und Stop Services und System
```shell sudo [-i] ``` - Superuser werden, ein Password ist nicht erforderlich. –i = permanent</br>
```shell sudo service <servicename> start|stop ```- Starten und Stoppen eines Services z.B. apache2, mysql</br>
```shell sudo shutdown –r now ```- Restart des Betriebssystems</br>
```shell sudo shutdown –h now ```- Stoppen des Betriebssystems</br>

#### Dateien bearbeiten und Filesystem
```shell ls, rm, mv, cd``` - Anzeigen, löschen, verschieben von Dateien und Wechsel Verzeichnis</br>
```shell nano oder [vi](http://debiananwenderhandbuch.de/vi.html) ```- Texteditoren</br>
```shell df –h, free –m, w ```- Diskbelegung, Speicherbelegung, Auslastung CPU</br>

#### Netzwerk
```shell ifconfig ``` – Ausgabe der eigenen IP-Adresse</br>
```shell netstat -a oder netstat -tulpen ```- Ausgabe der verwendeten Network Ports</br>
```shell net lookup <hostname>``` - IP-Adresse für Hostname ausgeben.</br>

#### Prozesse
```shell ps -ef oder top ```- Anzeige der aktiven Prozesse</br>
```shell kill <pid>``` - Prozess laut Prozess-Id (Nummer) beenden</br>

#### Hilfsprogramme
```shell curl http://<server> ``` - Aufruf einer Webseite oder eines HTTP REST Services</br>
```shell wget http://<server>/<datei> ```- kopieren einer Datei von einem Webserver</br>
```shell dos2unix <Datei> ```- Datei vom DOS ins UNIX/Linux Format umwandeln. Wird immer dann benötigt wenn eine Datei von Windows nach Linux kopiert wird und überflüssige CR enthält.</br>

### Advanced Packaging Tool (APT)

```shell sudo apt-get update- Repositories aktualisieren```
```shell sudo apt-get -y install apache2 - Webserver Apache installieren```
```shell sudo apt-get -y upgrade- bestehende Software aktualisieren```
```shell sudo apt-get -y autoremove - Aufräumen, nicht mehr benötigte Software entfernen```
```shell sudo apt-cache search [keyword] - Suchen nach einem bestimmen Programmpaket.```
```shell sudo dpkg -i [Programmpaket] - Installieren eines vorher downloadeten Programmpaketes```
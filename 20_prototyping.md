# BIST M300 | L.Widmer
## 20 Prototyping
### Vagrantfile erstellen
```shell
1. mkdir Ordnername
2. cd Ordnername
3. vagrant init ubuntu/trusty64
4. vagrant up --provider virtualbox
5. vagrant ssh
```
### Portweiterleitung einrichten
1. VirtualBox öffnen 
2. Auf den Reiter Ändern
3. Unter Netzwerk auf erweiterte Einstellungen
4. Und Angaben wie im Bild anpassen
   
![Portweiterleitung](/Bilder/Portweiterleitung.png)

### Advanced Packaging Tool (APT)
Das Advanced Packaging Tool (APT) ist ein Paketverwaltungssystem, das im Bereich des Betriebssystems Debian GNU/Linux entstanden ist und dpkg zur eigentlichen Paketverwaltung benutzt. Ziel ist es, eine einfache Möglichkeit zur Suche, Installation und Aktualisierung von Programmpaketen zur Verfügung zu stellen.
```shell
sudo apt-get update- Repositories aktualisieren
sudo apt-get -y install apache2 - Webserver Apache installieren
sudo apt-get -y upgrade- bestehende Software aktualisieren
sudo apt-get -y autoremove - Aufräumen, nicht mehr benötigte Software entfernen
sudo apt-cache search [keyword] - Suchen nach einem bestimmen Programmpaket.
sudo dpkg -i [Programmpaket] - Installieren eines vorher downloadeten Programmpaketes
```

## 220 MySQL & Apache
### Apache 
Der Apache HTTP Server ist ein quelloffenes und freies Produkt der Apache Software Foundation und der meistbenutzte Webserver im Internet.

Der Apache-Server kann sehr gut mit sogenannten Modulen erweitert werden, die bestimmte Zusatzfunktionen mitbringen und immer mit 'mod_' beginnen (z. B. mod_rewrite, mod_php5, mod_ssl).

Es gibt Module u. a. für

..*SSL (mod_ssl für OpenSSL, mod_gnutls für GnuTLS)
..*Einbindung und Verwendung von dynamischen Skriptsprachen (u. a. mod_php5, mod_perl, mod_python)
..*Unterstützung von zusätzlichen Protokollen (WebDAV: mod_dav, mod_dav_fs, mod_dav_lock, mod_dav_repos)
..*Authentifizierung (mod_auth*)
..*Weiterleitung an andere Server (mod_proxy)

#### Apache installieren
```shell
sudo apt-get install apache2 apache2-doc 
sudo a2enmod cgi
sudo service apache2 restart
```
### Rest
Representational State Transfer (abgekürzt REST, seltener auch ReST) bezeichnet ein Programmierparadigma für verteilte Systeme.
REST ist eine Abstraktion der Struktur und des Verhaltens des World Wide Web (HTTP GET, PUT, POST, DELETE).
REST hat das Ziel, einen Architekturstil zu schaffen, der die Anforderungen des modernen Web besser darstellt. Dabei unterscheidet sich REST vor allem in der Forderung nach einer einheitlichen Schnittstelle von anderen Architekturstilen.

![REST](/Bilder/rest.png)

### Common Gateway Interface (CGI)
Das Common Gateway Interface (CGI) ist ein Standard für den Datenaustausch zwischen einem Webserver und dritter Software, die Anfragen bearbeitet. CGI ist eine schon länger bestehende Variante, Webseiten dynamisch bzw. interaktiv zu machen, deren erste Überlegungen auf das Jahr 1993 zurückgehen.

#### Installation
```shell
sudo cp rest.txt /usr/lib/cgi-bin/rest
sudo mkdir /var/www/html/data
sudo chown www-data:www-data /var/www/html/data
sudo chmod +x /usr/lib/cgi-bin/rest
sudo apt-get insstall dos2unix
sudo dos2unix /usr/lib/cgi-bin/rest # evtl. DOS (CR) Zeichen entfernen
```

## MySQL
### Installation Datenbank
``` sudo apt-get install mysql-server mysql-client```
Beim der Abfrage nach dem root Password für den Admin User kann ein beliebiges Password angegeben werden. Dieses auf jeden Fall notieren!

### Konfiguration
Anmelden bei der Datenbank
``` mysql -u root -p```
auf dem mysql Prompt mysql>, Datenbank anlegen

``` create database if not exists sensoren;```
Neuen Datenbank-Benutzer www-data (gleicher Benutzername wie Apache Server) mit dem Kennwort "mbed" erstellen
```shell
create user 'www-data'@'localhost' identified by 'mbed'; 
grant usage on *.* to 'www-data'@'localhost' identified by 'mbed';
```
Zugriffe auf die neue Datenbank für den Benutzer www-data erlauben:
```shell
grant all privileges on sensoren.* to 'www-data'@'localhost';
flush privileges;
```
Datenbank wechseln

use sensoren;
Tabelle für die Sensordaten erstellen

``` create table data ( seq INT PRIMARY KEY AUTO_INCREMENT, poti FLOAT, light FLOAT, hall FLOAT, temp FLOAT, created TIMESTAMP DEFAULT CURRENT_TIMESTAMP ```
Testdaten schreiben und lesen
```shell
insert into data(poti, light, hall, temp) values ( 0.9, 0.8, 0.49, 25.2 );
insert into data(poti, light, hall, temp) values ( 0.8, 0.7, 0.48, 25.1 );
# lesen (alle Daten)
select * from data;
# Mittelwert vom Temperaturwert ausgeben
select avg(temp) from data;
# Kleinster Wert vom Temperaturwert ausgeben
select min(temp) from data;
# Grösster Wert vom  Temperaturwert ausgeben
select max(temp) from data;
Abmelden
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

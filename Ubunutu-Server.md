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

## Nützliche Befehle

### Administrator, Start und Stop Services und System

```shell sudo [-i] ``` - Superuser werden, ein Password ist nicht erforderlich. –i = permanent
```shell sudo service <servicename> start|stop ```- Starten und Stoppen eines Services z.B. apache2, mysql
```shell sudo shutdown –r now ```- Restart des Betriebssystems
```shell sudo shutdown –h now ```- Stoppen des Betriebssystems.

### Dateien bearbeiten und Filesystem
```shell ls, rm, mv, cd``` - Anzeigen, löschen, verschieben von Dateien und Wechsel Verzeichnis
```shell nano oder [vi](http://debiananwenderhandbuch.de/vi.html) ```- Texteditoren
```shell df –h, free –m, w ```- Diskbelegung, Speicherbelegung, Auslastung CPU

### Netzwerk
```shell ifconfig ``` – Ausgabe der eigenen IP-Adresse
```shell netstat -a oder netstat -tulpen ```- Ausgabe der verwendeten Network Ports
```shell net lookup <hostname>``` - IP-Adresse für Hostname ausgeben.

### Prozesse
```shell ps -ef oder top ```- Anzeige der aktiven Prozesse
```shell kill <pid>``` - Prozess laut Prozess-Id (Nummer) beenden

### Hilfsprogramme

```shell curl http://<server> ``` - Aufruf einer Webseite oder eines HTTP REST Services
```shell wget http://<server>/<datei> ```- kopieren einer Datei von einem Webserver
```shell dos2unix <Datei> ```- Datei vom DOS ins UNIX/Linux Format umwandeln. Wird immer dann benötigt wenn eine Datei von Windows nach Linux kopiert wird und überflüssige CR enthält.
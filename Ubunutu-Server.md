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
```shell
sudo [-i] - Superuser werden, ein Password ist nicht erforderlich. –i = permanent
sudo service <servicename> start|stop - Starten und Stoppen eines Services z.B. apache2, mysql
sudo shutdown –r now - Restart des Betriebssystems
sudo shutdown –h now - Stoppen des Betriebssystems.
```
### Dateien bearbeiten und Filesystem
```shell
ls, rm, mv, cd - Anzeigen, löschen, verschieben von Dateien und Wechsel Verzeichnis
nano oder [vi](http://debiananwenderhandbuch.de/vi.html) - Texteditoren
df –h, free –m, w - Diskbelegung, Speicherbelegung, Auslastung CPU
```
### Netzwerk
```shell
ifconfig – Ausgabe der eigenen IP-Adresse
netstat -a oder netstat -tulpen - Ausgabe der verwendeten Network Ports
net lookup <hostname> - IP-Adresse für Hostname ausgeben.
```

### Prozesse
```shell
ps -ef oder top - Anzeige der aktiven Prozesse
kill <pid> - Prozess laut Prozess-Id (Nummer) beenden
```
### Hilfsprogramme
```shell
curl http://<server> - Aufruf einer Webseite oder eines HTTP REST Services
wget http://<server>/<datei> - kopieren einer Datei von einem Webserver
dos2unix <Datei> - Datei vom DOS ins UNIX/Linux Format umwandeln. Wird immer dann benötigt wenn eine Datei von Windows nach Linux kopiert wird und überflüssige CR enthält.
```
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
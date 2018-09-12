#Ubunut Server VM einrichten | L.Widmer
## Vagrantfile erstellen
```shell
1. mkdir Ordnername
2. cd Ordnername
3. vagrant init ubuntu/trusty64
4. vagrant up --provider virtualbox
5. Vagrant starten --> vagrant ssh
```
## Portweiterleitung einrichten
1. VirtualBox öffnen 
2. Ändern der VM Einstellungen unter Netzwerk/Erweiterte Einstellungen/Port Weiterleitung
   ![Portweiterleitung](/Bilder/Portweiterleitung.png)
# BIST M300 | L.Widmer
## 30 Infrastruktur automatisieren
### Infrastructure as Code (IaC)
"Infrastructure as Code" ist ein Paradigma zur Infrastruktur-Automation basierend auf Best Practices von der Softwareentwicklung.
Im Vordergrund stehen konsistente und wiederholbare Definitionen für die Bereitstellung von Systemen und deren Konfiguration.
Dies bedeutet, dass wenn man ein Server mit Vagrant erstellt, kann man im Vagrantfile die Datei bearbeiten und so die Virtuelle Maschine konfigurieren. 

```shell
Vagrant.configure(2) do |config|
config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"  
  end
```

Damit es eine schönere Struktur hat, habe ich Apache in einem zweiten File mit dem Namen Bootstrap.sh erstellt.
In dieser Datei installiert er Apache und löscht wenn etwas im Verzeichnis /var/www ist, dieses.

```shell
#!/usr/bin/env bash

apt-get update
apt-get install -y apache2
if ! [ -L /var/www ]; then
  rm -rf /var/www
  ln -fs /vagrant /var/www
fi
```

Sofern nun beide Dateien erstellt sind kann man die Virtuelle Maschine löschen mit dem Befehl ``` vagrant destroy ``` und eine neue starten mit dem Befehl ``` vagrant up```

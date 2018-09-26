# BIST M300 | L.Widmer
## 30 Infrastruktur automatisieren
### Infrastructure as Code (IaC)
"Infrastructure as Code" ist ein Paradigma zur Infrastruktur-Automation basierend auf Best Practices von der Softwareentwicklung.
Im Vordergrund stehen konsistente und wiederholbare Definitionen für die Bereitstellung von Systemen und deren Konfiguration.
Dies bedeutet, dass wenn man ein Server mit Vagrant erstellt, kann man im Vagrantfile die Datei bearbeiten und mit ein paar wenigen Zeilen zum Beispiel ein Apache Service installieren.


``Vagrant.configure(2) do |config|
config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest:80, host:8080, auto_correct: true
  config.vm.synced_folder ".", "/var/www/html"  
 config.vm.provider "virtualbox" do |vb|
  vb.memory = "512"  
 end

  config.vm.provision "shell", inline: <<-SHELL 
    sudo apt-get update
    sudo apt-get -y install apache2
  SHELL
end``
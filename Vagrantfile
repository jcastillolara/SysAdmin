# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.define "vm1" do |vm1|
      vm1.vm.box = "ubuntu/focal64"
      vm1.vm.hostname = "wordpress"
      vm1.vm.provision "shell", inline: <<-SHELL
        apt-get update >/dev/null 2>&1
        apt-get install -y apache2 >/dev/null 2>&1
        echo "ubuntu1" >> /var/www/html/whoami.html
        echo "WHO AM I??"
        curl -s http://localhost/whoami.html
      SHELL
  
    end
  
    config.vm.define "vm2" do |vm2|
      vm2.vm.box = "ubuntu/focal64"
      vm2.vm.hostname = "elasticsearch"
      vm2.vm.provision "shell", path: "configure.sh"
    end
  end
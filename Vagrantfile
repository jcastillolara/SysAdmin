# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.define "wordpress" do |wordpress|
      wordpress.vm.box = "ubuntu/focal64"
      wordpress.vm.hostname = "wordpress"
      wordpress.vm.provision "shell", inline: <<-SHELL
        apt-get update >/dev/null 2>&1
        apt-get install -y apache2 >/dev/null 2>&1
  
      SHELL
  
    end
  
    config.vm.define "elasticsearch" do |elasticsearch|
      elasticsearch.vm.box = "ubuntu/focal64"
      elasticsearch.vm.hostname = "elasticsearch"
      elasticsearch.vm.provision "shell", path: "configure.sh"
    end
  end
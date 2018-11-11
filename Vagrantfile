# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.network :forwarded_port, guest: 50600, host: 8080

  config.vm.synced_folder ".", "/home/vagrant/yotei"

  config.vm.provision "docker"
  config.vm.provision "shell", inline: <<-SHELL
    curl -L "https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m)" >  ~/docker-compose
    sudo mv ~/docker-compose /usr/local/bin/docker-compose
    sudo chown root:root /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
  SHELL
end


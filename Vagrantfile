# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "ubuntu/trusty64"
  locale = "fr_FR.UTF.8"
  
  config.vm.network "private_network", ip: "192.168.33.15"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--name", "essai", "--memory", "2048"]
  end
  
  # 
  # Installation de ansible
  config.vm.provision "shell", inline: <<-SHELL
	sudo apt-get -y install software-properties-common
	sudo apt-add-repository ppa:ansible/ansible
	sudo apt-get update
	sudo apt-get install -y ansible
	sudo apt-get install -y git
  SHELL
end
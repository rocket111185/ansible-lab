# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "vagrant-ubuntu2004"
  config.vm.define "ubuntu2004"
  config.vm.network "forwarded_port", guest: 80, host: 2023

  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu2004"
    vb.memory = "2048"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.inventory_path = "inventory/"
    ansible.limit = "localhost"
  end

end

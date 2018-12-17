# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = "2"
  end

  config.vm.define "k8s-master" do |db|
    db.vm.network :private_network, ip: "192.168.99.11"
    db.vm.hostname = "k8s-master"
  end

  config.vm.define "k8s-node1" do |www|
    www.vm.network :private_network, ip: "192.168.99.12" 
    www.vm.hostname = "k8s-node1"
  end

  config.vm.define "k8s-node2" do |www|
    www.vm.network :private_network, ip: "192.168.99.13"
    www.vm.hostname = "k8s-node2"
  end

  config.vm.provision "shell", inline: <<-SHELL
     adduser ansible
     mkdir -p /home/ansible/.ssh
     cat /vagrant/vagrant_rsa.pub >> /home/ansible/.ssh/authorized_keys
     chown ansible /home/ansible/.ssh/authorized_keys
     chgrp ansible /home/ansible/.ssh/authorized_keys
     echo "ansible ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/ansible
  SHELL

end


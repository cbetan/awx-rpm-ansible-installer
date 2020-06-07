# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "centos7" do |centos7|
    centos7.vm.box = "geerlingguy/centos7"
    centos7.vm.network "forwarded_port", guest: 80, host: 8008, host_ip: "127.0.0.1"
    centos7.vm.network "forwarded_port", guest: 22, host: 2222, host_ip: "127.0.0.1"
    centos7.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
    end
    centos7.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "awx-setup.yml"
    end
  end

  config.vm.define "centos8" do |centos8|
    centos8.vm.box = "geerlingguy/centos8"
    centos8.vm.network "forwarded_port", guest: 80, host: 8009, host_ip: "127.0.0.1"
    centos8.vm.network "forwarded_port", guest: 22, host: 2223, host_ip: "127.0.0.1"
    centos8.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
    end
    centos8.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "awx-setup.yml"
    end
  end

end

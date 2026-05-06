# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

###  TARGET VM ########
  config.vm.define "target" do |target|
    target.vm.box = "bento/almalinux-9"
    target.vm.box_version = "202511.24.0"
    target.vm.hostname = "target-server"
    target.vm.network "private_network", ip: "192.168.56.10"
    target.vm.synced_folder ".", "/vagrant", disabled: true
    target.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 1
    end
  end
  ######## ATTACKER #######
  config.vm.define "kali" do |kali|
    
    kali.vm.box = "kalilinux/rolling"
    kali.vm.box_version = "2026.1.0"
    kali.vm.network "private_network", ip: "192.168.56.20"
    kali.vm.synced_folder ".", "/vagrant", disabled: true
    kali.vm.provider "virtualbox" do |vb| 
      vb.gui = true 
      vb.cpus = 2
      vb.memory = "2048"
    end
  end
  
  ###### SIEM MACHINE / WAZUH ########
  config.vm.define "wazuh" do |siem|
    siem.vm.box = "bento/ubuntu-22.04"
    siem.vm.hostname = "wazuh-manager"
    siem.vm.network "private_network", ip: "192.168.56.30"
    siem.vm.synced_folder ".", "/vagrant", disabled: true
    siem.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
      vb.cpus = 2
    end
  end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end

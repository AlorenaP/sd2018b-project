# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
   config.vm.box = "centos1706_v0.2.0"

   config.vm.network "forwarded_port", guest: 8080, host: 8080
  
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
   config.vm.network "private_network", ip: "192.168.33.10"

  
   config.vm.provider "virtualbox" do |vb|
     vb.memory = "2024"
     vb.cpus=2
   end
   config.vm.define "prueba" do |prueba|
    prueba.vm.provision "ansible" do |ansible|
      ansible.verbose = 'vvv'
      ansible.playbook = "ansible/infraestructure.yml"
    end
  end
end

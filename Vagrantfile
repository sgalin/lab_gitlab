# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "gitlab"
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "forwarded_port", guest: 80, host: 80
  #config.vm.provision "shell", path: "initial_setup.sh"
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/main.yml"
  end
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.linked_clone = true
    vb.cpus = 2
    vb.memory = "4096"
    vb.name = "gitlab"
    vb.customize ["modifyvm", :id, "--audio", "none"]
  end
end
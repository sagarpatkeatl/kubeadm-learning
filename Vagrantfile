# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/debian10"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'playbook.yml'
  end

  config.vm.define :node1 do |n|
    n.vm.network :private_network, ip: '192.168.100.11'
  end

  config.vm.provider :virtualbox do |v|
    v.cpus = 2
  end
end

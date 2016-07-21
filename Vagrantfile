# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

N = 4
(1..N).each do |machine_id|
Vagrant.configure("2") do |config|
  config.vm.define "machine#{machine_id}" do |machine|
    machine.vm.hostname = "machine#{machine_id}"
    machine.vm.box = "debian/jessie64"
    machine.vm.provider :lxc do |lxc|
      lxc.customize "network.ipv4", "192.168.122.#{20+machine_id}/24"
     end
 
 ## Ansible Provisioning
 ##
   if machine_id == N
   machine.vm.provision "ansible" do |ansible|
     ansible.verbose = "vvvv"
     ansible.inventory_path = "./inventory"
     ansible.sudo = true
     ansible.limit = "all"
     ansible.playbook = "site.yml"
            end
         end
      end
   end
end

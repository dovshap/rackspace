# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "mysql" do |mysql|
    mysql.vm.box = "debian/jessie64"
  end
  config.vm.define "web" do |web|
    web.vm.box = "debian/jessie64"
  end
 
 ## Ansible Provisioning
 ##
   config.vm.provision "ansible" do |ansible|
     ansible.verbose = "vvvv"
     ansible.sudo = true
     ansible.limit = "all"
     ansible.playbook = "site.yml"
   end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :
# Sample Vagranfile to setup Learning Environment
# for Ansible Playbook Essentials
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.hostmanager.enabled = true
#	config.hostmanager.manage_host = true
	config.hostmanager.manage_guest = true
	config.hostmanager.ignore_private_ip = false
	config.hostmanager.include_offline = true

	config.vm.define "rhevm" do |db|
		db.vm.box = "centos/6"
		db.vm.hostname = "rhevm"
		db.vm.network "private_network", ip: "11.0.0.3"
		db.vm.provider "virtualbox" do |v|
			v.memory = 4096
			v.cpus = 1
		end
		db.vm.provision "shell", inline: "cat /vagrant/.ssh/id_rsa.pub >> ~vagrant/.ssh/authorized_keys" 
#		config.vm.provision :ansible do |ansible|
#			ansible.playbook = "setup_RHEVM.yml"
#		end
	end
	
	config.vm.define "rhevp1" do |db|
		db.vm.hostname = "rhevp1"
		db.vm.network :private_network, ip: "11.0.0.1"
		db.vm.provider "virtualbox" do |v|
			v.memory = 1024
			v.cpus = 1
		end
	end
	
	config.vm.define "rhevh1" do |db|
		db.vm.hostname = "rhevh1"
		db.vm.network :private_network, ip: "11.0.0.4"
		db.vm.provider "virtualbox" do |v|
			v.memory = 1024
			v.cpus = 1
		end
	end
	
	config.vm.define "rhevh2" do |db|
		db.vm.hostname = "rhevh2"
		db.vm.network :private_network, ip: "11.0.0.5"
		db.vm.provider "virtualbox" do |v|
			v.memory = 1024
			v.cpus = 1
		end
	end
end


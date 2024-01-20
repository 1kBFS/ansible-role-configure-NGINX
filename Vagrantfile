# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :node1 do |node1|
  	node1.vm.provider "virtualbox" do |vb|
  		vb.memory = "1024"
  	end
  	node1.vm.network "private_network", ip: "192.168.56.10"
  	node1.vm.box = "ubuntu/jammy64"
  end
  config.vm.define :node2 do |node2|
  	node2.vm.provider "virtualbox" do |vb|
  		vb.memory = "1024"
  	end
  	node2.vm.network "private_network", ip: "192.168.56.11"
  	node2.vm.box = "centos/7"
  end
  config.vm.define :node3 do |node3|
  	node3.vm.provider "virtualbox" do |vb|
  		vb.memory = "1024"
  	end
  	node3.vm.network "private_network", ip: "192.168.56.12"
  	node3.vm.box = "archlinux/archlinux"
  end
end

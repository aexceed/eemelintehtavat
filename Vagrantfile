# -*- mode: ruby -*-
# vi: set ft=ruby :

$minion = <<MINION
sudo apt-get update
sudo apt-get -qy install salt-minion
echo "master: 192.168.12.3">/etc/salt/minion
sudo service salt-minion restart
MINION

$master = <<MASTER
sudo apt-get update
sudo apt-get -qy install salt-master
MASTER

Vagrant.configure("2") do |config|
	config.vm.box = "debian/bullseye64"
	config.vm.define "debian" do |debian|
		debian.vm.provision :shell, inline: $minion
		debian.vm.network "private_network", ip: "192.168.12.100"
		debian.vm.hostname = "debian"
	end
	
	config.vm.box = "ubuntu/jammy64"
	config.vm.define "ubuntu" do |ubuntu|
		ubuntu.vm.provision :shell, inline: $minion
		ubuntu.vm.network "private_network", ip: "192.168.12.102"
		ubuntu.vm.hostname = "ubuntu"
	end
	
	config.vm.box = "centos/7"
	config.vm.define "centos" do |centos|
		centos.vm.provision :shell, inline: $minion
		centos.vm.network "private_network", ip: "192.168.12.104"
		centos.vm.hostname = "centos"
	end
	
	config.vm.box = "ubuntu/jammy64"
	config.vm.define "emaster", primary: true do |emaster|
		emaster.vm.provision :shell, inline: $master
		emaster.vm.network "private_network", ip: "192.168.12.3"
		emaster.vm.hostname = "emaster"
	end
	
	config.vm.box = "ubuntu/trusty64"
	config.vm.define "ubuntuserver" do |ubuntuserver|
		ubuntuserver.vm.provision :shell, inline: $minion
		ubuntuserver.vm.network "private_network", ip: "192.168.12.106"
		ubuntuserver.vm.hostname = "ubuntuserver"
	end

	config.vm.box = "opentable/win-2012r2-standard-amd64-nocm"
	config.vm.define "windowsserver" do |windowsserver|
		windowsserver.vm.provision :shell, inline: $minion
		windowsserver.vm.network "private_network", ip: "192.168.12.108"
		windowsserver.vm.hostname = "windowsserver"
		config.winrm.max_tries = 300
	end

	config.vm.box = "gusztavvargadr/windows-10"
	config.vm.define "windows10" do |windows10|
		windows10.vm.provision :shell, inline: $minion
		windows10.vm.network "private_network", ip: "192.168.12.110"
		windows10.vm.hostname = "windows10"
		config.winrm.max_tries = 300
	end
end

## Kiitokset pohjasta Terolle @ https://terokarvinen.com/

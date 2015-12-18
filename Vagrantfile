# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
# The most common configuration options are documented and commented below.
# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.

# Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.

	config.vm.define "oam" do |oam|
	
		oam.vm.box = "esa-oam"
		oam.vm.box_url="http://esaserver01.cei.cox.com/vagrant/esa-oam/"
		oam.vm.hostname="esa02.esadvisory.com"
		oam.vm.box_check_update = false
		#oam.vm.network "public_network"
		oam.ssh.insert_key=false
		oam.ssh.username = 'vagrant'
		oam.ssh.password = 'vagrant'
		oam.ssh.forward_x11=true
		oam.vm.provider "virtualbox" do |vb|
		#vb.gui = true
			vb.cpus = 2
			vb.memory = "2048"
	end
  end

  config.vm.define "db" do |db|
  
		db.vm.box = "esa-odb2"
		db.vm.hostname="esa01.esadvisory.com"
		db.vm.box_check_update = false
		#db.vm.network "public_network"
		db.vm.network "private_network", ip: "192.168.33.10"
		db.ssh.insert_key=false
		db.ssh.username = 'vagrant'
		db.ssh.password = 'vagrant'		
		db.ssh.forward_x11=true
		
		db.vm.provider "virtualbox" do |vb|
#   vb.gui = true
			vb.cpus = 2
			vb.memory = "2048"
	end
		
  end


	# config.vm.synced_folder "../data", "/vagrant_data"


#



# Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
# such as FTP and Heroku are also available. See the documentation at
# https://docs.vagrantup.com/v2/push/atlas.html for more information.
# config.push.define "atlas" do |push|
#   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
# end


# config.vm.provision "shell", inline: <<-SHELL
#   sudo apt-get update
#   sudo apt-get install -y apache2
# SHELL
end

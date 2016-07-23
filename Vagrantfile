# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.synced_folder "app", "/home/vagrant/app"

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate//vagrant","1"]
    vb.customize ["modifyvm", :id, "--memory", 512]
  end
  config.vm.provision "chef_solo" do |chef|
    chef.cookbooks_path = ["./mycookbook/cookbooks"]
	chef.add_recipe "apt"
	chef.add_recipe "build-essential"
	chef.add_recipe "mongodb"
	chef.add_recipe "nodejs"

	chef.json = {
		"nodejs" => {
		"version" => "0.10.26"
		}
	}
  end
end

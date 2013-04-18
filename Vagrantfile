# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  #config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.data_bags_path = "data_bags"
    chef.add_recipe "git"
    chef.add_recipe "vim"
    chef.add_recipe "homesick::data_bag"

    chef.json = {
       :users => ['vagrant']
    }
  end
end

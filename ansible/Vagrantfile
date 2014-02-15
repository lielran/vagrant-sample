 #-*- mode: ruby -*-
 #vi: set ft=ruby :
#require 'vagrant-ansible'


Vagrant.configure("2") do |config|
  #config.vm.box = "centos6.5"
  #config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.1/centos65-x86_64-20131205.box"
  config.vm.box = "precise32"
  config.vm.box_url =  "http://files.vagrantup.com/precise32.box"
  config.vm.network :forwarded_port, host: 4567, guest: 80

 config.vm.define "server" do |server|

    server.vm.box = config.vm.box
    server.vm.network :private_network, ip: "192.168.55.55"
   
    server.vm.provision "ansible" do |ansible|

      ansible.playbook = "provisioning/apache.yml"
      ansible.inventory_path = "provisioning/hosts"
      ansible.verbose = true
      ansible.sudo = true
    end
  end

end

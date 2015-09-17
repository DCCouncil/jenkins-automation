# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # vbox name
  config.vm.box = "ubuntu/trusty64"

  # port forwarding
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.groups = {
      "vagrant" => ["default"]
    }
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end
end

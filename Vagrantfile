# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # set base vagrant box
  config.vm.box = "centos/7"

  # set forwarding for Kibana access
  config.vm.network "forwarded_port", guest: 5601, host: 5601, host_ip: "127.0.0.1"

  # configure virtualbox horsepower specs
  config.vm.provider "virtualbox" do |v|
    v.name = "es_playground"
    v.gui = false
    v.memory = "4096"
    v.cpus = 2
  end

  # set ansible playbook post-install provisioning
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end

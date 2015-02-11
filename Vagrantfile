# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |cluster|
  cluster.vm.define :dbc1 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.5"
  end

  cluster.vm.define :dbc2 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.4"
  end

#  cluster.vm.define :pgpool do |config|
#    config.vm.box = "ubuntu/trusty64"
#    config.vm.network "private_network", ip: "10.0.0.3"
#  end

#  cluster.vm.define :web1 do |config|
#    config.vm.box = "ubuntu/trusty64"
#    config.vm.network "private_network", ip: "10.0.0.2"
#  end

  cluster.vm.provision :ansible do |ansible|
    ansible.playbook = "provision.yml"
    ansible.groups = {
      "dbc-primary" => ["dbc1"],
      "dbc-replica" => ["dbc2"],
#      "dbc-pgpool" => ["pgpool"],
#      "application" => ["web1"],
    }
  end
end

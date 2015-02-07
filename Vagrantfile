# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |cluster|
  cluster.vm.define :dbc1 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.5"
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "db-primary.yml"
    end
  end

  cluster.vm.define :dbc2 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.4"
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "db-replica.yml"
    end
  end

  # DBC Cluster
  cluster.vm.define :pgpool do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.3"
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "db-pgpool.yml"
    end
  end

  cluster.vm.define :web1 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network "private_network", ip: "10.0.0.2"
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "application.yml"
    end
  end
end


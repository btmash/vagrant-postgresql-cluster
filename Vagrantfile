# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :dbc1 do |dbc1_config|
    dbc1_config.vm.box = "ubuntu/trusty64"
    dbc1_config.vm.network "private_network", ip: "10.0.0.5"
  end

  config.vm.define :dbc2 do |dbc2_config|
    dbc2_config.vm.box = "ubuntu/trusty64"
    dbc2_config.vm.network "private_network", ip: "10.0.0.4"
  end

  # DBC Cluster
  config.vm.define :pgpool do |pgpool_config|
    pgpool_config.vm.box = "ubuntu/trusty64"
    pgpool_config.vm.network "private_network", ip: "10.0.0.3"
  end

  config.vm.define :web1 do |web1_config|
    web1_config.vm.box = "ubuntu/trusty64"
    web1_config.vm.network "private_network", ip: "10.0.0.2"
  end
end


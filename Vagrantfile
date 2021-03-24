# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.

  # Uncomment for Ubuntu
  config.vm.box = "bento/ubuntu-18.04"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Comment out the following for `users` role
  # which requires vagrant user login (a default feature)
  #config.ssh.username = 'tetter'
  #config.ssh.private_key_path = <full path to your private key>

  config.vm.define 'cp-vm' do |machine|
    machine.vm.hostname = 'cp1-cp1'
    machine.vm.network "private_network", ip: '172.16.94.10'
  end

  config.vm.define 'node-1' do |machine|
    machine.vm.hostname = 'cp-node1'
    machine.vm.network "private_network", ip: '172.16.94.11'
  end

  config.vm.define 'node-2' do |machine|
    machine.vm.hostname = 'cp-node2'
    machine.vm.network "private_network", ip: '172.16.94.12'
  end

  config.vm.define 'node-3' do |machine|
    machine.vm.hostname = 'cp-node3'
    machine.vm.network "private_network", ip: '172.16.94.13'
  end
end

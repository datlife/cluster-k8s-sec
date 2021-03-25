# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  config.vm.box = "bento/ubuntu-18.04"
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end

  ## Set up Control Plane (master node) ##
  config.vm.define 'cp1-cp1' do |machine|
    machine.vm.hostname = 'cp1-cp1'
    machine.vm.network "private_network", ip: "172.16.94.10"
    machine.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbooks/master-k8s-setup.yml"
    end
  end

  ## Set up worker nodes ##
  # (1..N).each do |i|
  #   config.vm.define "c1-node#{i}" do |machine|
  #   machine.vm.hostname = "c1-node#{i}"
  #   machine.vm.network "private_network", ip: "172.16.94.#{10 + i}"
  # end

    # config.vm.provision :ansible do |ansible|
    #   # set playbook to execute on `vagrant provision`
    #   ansible.playbook = "playbooks/setup_k8s.yml"
    #   ansible.sudo = true
    #   ansible.verbose = 'vv'
end

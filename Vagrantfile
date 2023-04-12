# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
    config.vbguest.no_install = true
  end

  config.vm.define "server1" do |server1|
    server1.vm.box = "ubuntu/jammy64"
    server1.vm.network "private_network", ip: "192.168.17.10"
    server1.vm.hostname = "server1"

    server1.vm.provider "virtualbox" do |vb|
      vb.memory = "3072"
      vb.cpus = "3"
    end

    server1.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

  # config.vm.define "server2" do |server2|
  #   server2.vm.box = "ubuntu/jammy64"
  #   server2.vm.network "private_network", ip: "192.168.17.11"
  #   server2.vm.hostname = "server1"

  #   server2.vm.provider "virtualbox" do |vb|
  #     vb.memory = "3072"
  #     vb.cpus = "3"
  #   end

  #   server2.vm.provision "ansible" do |ansible|
  #     ansible.playbook = "playbook.yml"
  #   end
  # end

end

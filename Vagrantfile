# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ac21/dev-vm-rails5"

  config.vm.box_check_update = true

  config.vm.provider "virtualbox" do |vb|
      vb.name = "dev-vm-rails5"
      vb.memory = "2048"
      vb.cpus = 1
      vb.customize ['modifyvm', :id, "--vram", "16"]
      vb.customize ['modifyvm', :id, "--vrde", "off"]
      vb.customize [ "guestproperty", "set", :id, "/VirtualBox/GuestAdd/VBoxService/--timesync-set-threshold", 5000]
  end

  config.dns.tld = 'dev'
  config.vm.hostname = 'dev-vm'

  config.vm.network 'private_network', ip: '192.168.101.99'
  config.vm.synced_folder '../', '/home/vagrant/repos'
  config.vm.synced_folder '.', '/vagrant'

  config.ssh.forward_agent = true

  config.vm.provision "shell", inline: <<-SHELL
  # nothing just yet
  SHELL

  config.vm.provision "shell", privileged: false, inline: <<-SCRIPT
    cp /vagrant/.Guardfile ~/.Guardfile
    cp /vagrant/.gitconfig ~/.gitconfig
  SCRIPT
end

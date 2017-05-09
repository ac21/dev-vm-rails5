# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ac21/dev-vm-rails5"

  config.vm.box_check_update = true

  config.vm.provider "virtualbox" do |vb|
      vb.name = "dev-vm-rails5"
      vb.memory = "2048"
      vb.cpus = 2
  end

  config.vm.synced_folder "../", "/home/ubuntu/repos"

  config.ssh.forward_agent = true

  # Enable provisioning with a shell script.
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get -y libcurl
  # SHELL
end

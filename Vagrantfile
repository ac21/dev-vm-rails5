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

  config.dns.tld = 'dev'
  config.vm.hostname = 'dev-vm'

  config.vm.network 'private_network', ip: '192.168.101.99'
  config.vm.synced_folder '../', '/home/vagrant/repos'

  config.ssh.forward_agent = true

  # Enable provisioning with a shell script.
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get install software-properties-common # debian only
    sudo add-apt-repository "deb https://cli-assets.heroku.com/branches/stable/apt ./"
    curl -L https://cli-assets.heroku.com/apt/release.key | sudo apt-key add -
    sudo apt-get update
    sudo apt-get install heroku
  SHELL

  config.vm.provision "shell", privileged: false, inline: <<-SCRIPT
    cp /vagrant/.Guardfile ~/.Guardfile
    cp /vagrant/.gitconfig ~/.gitconfig
  SCRIPT
end

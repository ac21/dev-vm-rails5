DEV-VM - reusable environment for all

Default Ruby Dev Environment.

Base Configuration is:

1. Ubuntu 16.04
2. Ruby 2.4
3. Rails 5.1
4. Postgres 9.5
5. Redis 3.2.8

## Setup

1. Fork this directory
2. Install Vagrant `https://www.vagrantup.com/`
3. Install VirtualBox `https://www.virtualbox.org/`
4. Install Vagrant-DNS `vagrant plugin install vagrant-dns`
5. Register the DNS server as a resolver `vagrant dns --install`
6. start vagrant with `vagrant up` to download and configure the box image
7. Login into vagrant using 'vagrant ssh`
8. customize `my-env.sh` to your preferences
9. configure `~/.gitconfig` as necessary

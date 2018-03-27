# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "AlbertZheng/vagrant-freebsd-4.4-i386-minimal"
  config.vm.guest = :freebsd

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  config.vm.box_check_update = true

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  #
  config.vm.network "forwarded_port", guest: 23, host: 2223, id: "telnet"
  
  config.ssh.insert_key = false
  config.ssh.shell = "sh"

  config.ssh.username = "root"
  #config.ssh.password = "vagrant"
  config.ssh.extra_args = ["-c3des-cbc", "-oKexAlgorithms=+diffie-hellman-group1-sha1", "-oHostKeyAlgorithms=+ssh-dss"]

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"


  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  #
  # Disable the default /vagrant share
  config.vm.synced_folder ".", "/vagrant", disabled: true


  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
      vb.memory = "1024"
      vb.cpus = "1"

      vb.customize ['modifyvm', :id, "--natdnshostresolver1", "on"]
      #vb.customize ["modifyvm", :id, "--nictype1", "virtio"]
  end
end

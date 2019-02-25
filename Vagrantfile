# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # the os to be installed and run in the virtual machine is ubunu 18.04 64bit
  config.vm.box = "ubuntu/bionic64"
  # Changing the host machine name to bioapache to overide the default(vagant)
  config.vm.hostname = "bioapache"
  # Configuring an IP to be used to access the virtual machine. In this case 
  # an IP from the class C private network address space
  config.vm.network "private_network", ip: "192.168.33.14"

  config.vm.provision "shell", inline: <<-SHELL
    # update the packages that came with the image installed
    apt-get update
    # Install apache server
    apt-get install -y apache2
    # Start the apache server after installation
    sudo /etc/init.d/apache2 start
  SHELL
end

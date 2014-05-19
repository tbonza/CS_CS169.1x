# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "hashicorp/precise64"

  # config.vm.provision :shell, :path => "bootstrap.sh"
  config.vm.network "private_network", ip: "192.168.56.105"
  
  # Use NFS for the shared folder
  config.vm.synced_folder ".", "/vagrant",
  id: "core",
  :nfs => true,
  :mount_options => ['nolock,vers=3,udp,noatime']
 
  # If using VirtualBox
  config.vm.provider :virtualbox do |vb|
  end
end

# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

MEMORY = 1024 # This matches the digital ocean droplet size
CPU_COUNT = 1

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "coralnexus/ubuntu-12.04-server-amd64"

  # private network
  config.vm.network "private_network", ip: "192.168.56.105"

  # forwarded port
  config.vm.network "forwarded_port", guest: 80, host: 3000

  # Use NFS for the shared folder
  config.vm.synced_folder ".", "/working",
  id: "core",
  :nfs => true,
  :nfs_export => true,
  :mount_options => ['nolock,vers=3,udp,noatime']
 
  # If using VirtualBox
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", MEMORY.to_s]
    vb.customize ["modifyvm", :id, "--cpus", CPU_COUNT.to_s]
  end

  # Provision the virtualbox
  config.vm.provision "shell",
  path: File.absolute_path("")+"/vm-setup/configure-image-0.10.2.sh";
end

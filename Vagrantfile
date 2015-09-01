# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
  config.vm.box = "jluck/dev-interview"
  
  #Mount the source code folder into the VM
  config.vm.synced_folder ".", "/home/vagrant/assignments"

  config.vm.provider "virtualbox" do |vb|
	  # Display the VirtualBox GUI when booting the machine
	  vb.gui = true
	
	  # Customize the amount of memory on the VM:
	  # 4GB of Memory
	  vb.memory = "4096"
	  # 2 CPUs
	  vb.cpus = 2
  end

end

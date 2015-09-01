# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
  config.vm.box = "jluck/dev-interview"
  
  #Mount the source code folder into the VM
  config.vm.synced_folder ".", "/home/vagrant/assignments"

  config.vm.provider "virtualbox" do |vb, override|
	  # Display the VirtualBox GUI when booting the machine
	  vb.gui = true
	
	  # Customize the amount of memory on the VM:
	  # 4GB of Memory
	  vb.memory = "4096"
	  # 2 CPUs
	  vb.cpus = 2
	  
	  #256MB of Video Ram
	  vb.customize ["modifyvm", :id, "--vram", "256"]
	  
	  #Set the resolution for the display
	  vb.customize ["setextradata", "global", "GUI/MaxGuestResolution", "any"]
      vb.customize ["setextradata", :id, "CustomVideoMode1", "2560x1600x32"]
      
      #Enable clipboard between host and guest
      vb.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
  end

end

# -*- mode: ruby -*-
# vi: set ft=ruby :

###########  Make sure required plugins are installed ###############
# This file requires vagrant-vbguest (https://github.com/dotless-de/vagrant-vbguest) plugin.
# This plugin installs the correct version of virtualbox guest additions for your virtualbox installation.
# This is needed to make the screen resolution match that of the host.

plugin_no = 0
required_plugins = %w( vagrant-vbguest )
required_plugins.each do |plugin|
  (system "vagrant plugin install #{plugin}"; plugin_no += 1) unless Vagrant.has_plugin? plugin
end
(puts "Installed #{plugin_no} new plugins. Please restart the last command."; exit ) if plugin_no > 0
######################################################################

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
  
  config.vbguest.no_remote = true

end

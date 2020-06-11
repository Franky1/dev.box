# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "uniqu3/devbox"
    config.vm.box_check_update = false
    config.vm.boot_timeout = 1800  # increased to 30 minutes

    # automatic guest plugin update disabled
    if Vagrant.has_plugin?("vagrant-vbguest")
        config.vbguest.auto_update = false
    end

    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "devbox"
    # config.vm.network "forwarded_port", guest: 3306, host: 3306 #MySQL
    config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    # Optional NFS. Make sure to remove other synced_folder line too
    #config.vm.synced_folder ".", "/var/www", :nfs => { :mount_options => ["dmode=777","fmode=666"] }

    config.vm.provider "virtualbox" do |virtualbox|
        virtualbox.name = "Dev.Box"
        virtualbox.gui = true
        virtualbox.memory = 4096
        virtualbox.cpus = 2
    end
end

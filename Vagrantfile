# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

    config.vm.box_url = "https://cdn.rawgit.com/abra/2d39a446ce476148810f/raw/f6ca6059525241790b1db6247720d4ab6998d911/metadata.json"

    config.vm.box = "mojo/box"

    config.vm.network "forwarded_port", guest: 3000, host: 3000

    config.vm.hostname = "mojobox"

    config.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--cpus", "2"]
        v.customize ["modifyvm", :id, "--memory", "1024"]
        v.customize ["modifyvm", :id, "--usb", "off"]
        v.customize ["modifyvm", :id, "--usbehci", "off"]
    end

    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.synced_folder "./public", "/home/vagrant/public", :mount_options => ["dmode=755", "fmode=644"]

end

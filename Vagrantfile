# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_SERVER_URL'] = 'http://vagrant.elab.pro'

#  config.vm.network "public_network", ip: "192.168.0.30", hostname: true, bridge: "en1: Realtek PCIe GbE Family Controller"

Vagrant.configure("2") do |config|
  config.vm.define "haproxy" do |haproxy|
    haproxy.vm.box = "ubuntu/jammy64"
    haproxy.vm.box_check_update = false
    haproxy.vm.hostname = "haproxy"
    haproxy.vm.network "public_network", ip: "192.168.0.30", hostname: true, bridge: "en1: Realtek PCIe GbE Family Controller"
    haproxy.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.provision "file", source: "/home/david/.ssh/ansible_key_rsa.pub", destination: "/home/vagrant/.ssh/"
    haproxy.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/ansible_key_rsa.pub
        cat /home/vagrant/.ssh/ansible_key_rsa.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "wordpress1" do |wordpress1|
    wordpress1.vm.box = "ubuntu/jammy64"
    wordpress1.vm.box_check_update = false
    wordpress1.vm.hostname = "wordpress1"
    wordpress1.vm.synced_folder ".", "/vagrant", disabled: true
    wordpress1.vm.network "public_network", ip: "192.168.0.31", hostname: true, bridge: "en1: Realtek PCIe GbE Family Controller"
    config.vm.provision "file", source: "/home/david/.ssh/ansible_key_rsa.pub", destination: "/home/vagrant/.ssh/"
    wordpress1.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/ansible_key_rsa.pub
        cat /home/vagrant/.ssh/ansible_key_rsa.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "wordpress2" do |wordpress2|
    wordpress2.vm.box = "ubuntu/jammy64"
    wordpress2.vm.box_check_update = false
    wordpress2.vm.hostname = "wordpress2"
    wordpress2.vm.synced_folder ".", "/vagrant", disabled: true
    wordpress2.vm.network "public_network", ip: "192.168.0.32", hostname: true, bridge: "en1: Realtek PCIe GbE Family Controller"
    config.vm.provision "file", source: "/home/david/.ssh/ansible_key_rsa.pub", destination: "/home/vagrant/.ssh/"
    wordpress2.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/ansible_key_rsa.pub
        cat /home/vagrant/.ssh/ansible_key_rsa.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "database" do |database|
    database.vm.box = "ubuntu/jammy64"
    database.vm.box_check_update = false
    database.vm.hostname = "database"
    database.vm.synced_folder ".", "/vagrant", disabled: true
    database.vm.network "public_network", ip: "192.168.0.33", hostname: true, bridge: "en1: Realtek PCIe GbE Family Controller"
    config.vm.provision "file", source: "/home/david/.ssh/ansible_key_rsa.pub", destination: "/home/vagrant/.ssh/"
    database.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/ansible_key_rsa.pub
        cat /home/vagrant/.ssh/ansible_key_rsa.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
end

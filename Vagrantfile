# -*- mode: ruby -*-
# vi: set ft=ruby :

# Every Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.
BOX_IMAGE = "ubuntu/bionic64"
NODE_COUNT = 3

Vagrant.configure("2") do |config|
  config.vm.define "master", primary: true do |subconfig|
    subconfig.vm.box = BOX_IMAGE
    subconfig.vm.hostname = "master"
    subconfig.vm.network :private_network, ip: "10.0.0.10"
  end

  (1..NODE_COUNT).each do |i|
    config.vm.define "node#{i}" do |subconfig|
      subconfig.vm.box = BOX_IMAGE
      subconfig.vm.hostname = "node#{i}"
      subconfig.vm.network :private_network, ip: "10.0.0.#{i + 10}"
    end
  end

  # Install avahi, hhvm on all machines  
#  config.vm.provision "shell", inline: <<-SHELL
#    apt-get update -y;
#    apt-get install -y avahi-daemon libnss-mdns;
#    apt-get install -y php;
#  SHELL

  # Use :ansible or :ansible_local to
  # select the provisioner of your choice
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/playbook.yml"
  end
end

#128
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.box_check_update = false

  config.vm.network "private_network", ip: "10.10.10.110"

  config.vm.synced_folder "./syncfiles", "/syncfiles", create: true
  config.vm.synced_folder ".", "/vagrant" , disabled: true
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # install latest npm and nodejs
  config.vm.provision "shell", inline: <<-SHELL
    echo "install nodejs npm" ;
    sudo apt install -y nodejs npm ;
    sudo npm config set strict-ssl false ;
    echo "install n" ;
    sudo npm install n -g ;
    echo "install newest nodejs npm" ;
    sudo n stable ;
    echo "uninstall outdated nodejs npm" ;
    sudo apt purge -y nodejs npm ;
    echo "Finished" ;
    exec $SHELL -l ;
  SHELL

end

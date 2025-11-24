# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  # Port forwarding for Django (runserver)
  config.vm.network "forwarded_port", guest: 8000, host: 8000

  # Provisioning script
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y python3-venv zip python3-pip

    # Alias python3 -> python for convenience
    echo "alias python='python3'" >> /home/vagrant/.bash_aliases
  SHELL
end

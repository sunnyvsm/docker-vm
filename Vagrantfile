# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 1313, host: 1313

  # shared folders for blog
  config.vm.synced_folder "../Blog/blog-source/", "/home/ubuntu/blog-source/"
  config.vm.synced_folder "../Blog/blog-release/", "/home/ubuntu/blog-release/"

  config.vm.provision "shell", inline: <<-SHELL
      # setup docker
      # taken from: https://docs.docker.com/engine/installation/linux/ubuntulinux/
      sudo apt-get update
      sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual -y
      sudo apt-get install apt-transport-https ca-certificates -y
      sudo apt-key adv --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
      sudo touch /etc/apt/sources.list.d/docker.list
      echo 'deb https://apt.dockerproject.org/repo ubuntu-xenial main' > /etc/apt/sources.list.d/docker.list
      sudo apt-get update
      sudo apt-get purge lxc-docker
      apt-cache policy docker-engine
      sudo apt-get install docker-engine -y
      sudo service docker start
   SHELL

end

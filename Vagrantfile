# -*- mode: ruby -*-
# vi: set ft=ruby :

# Lab 4
# v1.0.0

# Vagrant do loop start

Vagrant.configure("2") do |config|

# use the Ubuntu vagrant template (aka "box")

 config.vm.box = "ubuntu/bionic64"

# port forward for the web server, we'll keep everything
# behind the nat network.

 config.vm.network "forwarded_port", guest: 80, host: 80

# Use the Vagrant Provisioner to install some of the packages
# needed for LAMP stack.
#

 config.vm.provision "shell", inline: <<-SHELL
 apt update
 apt install -y apache2
 apt-get install -y mariadb-server
 apt-get install -y php
 apt-get install -y libapache2-mod-php
 apt-get install -y php-mysql
 your commands go here to to install additional package for LAMP

 SHELL

# For practice, let's have Vagrant copy a file out to the server.
# This file won't do anything, but is just an example of how we could
# Transfer a file of database users for example.  Some future
# automation would use add users to the database.  
# On your windows or mac, create an empty text file named "users.sql"
# put it in the SAME DIRECTORY as where this Vagrantfile is located.
# Then have Vagrant copy it out to the server.
# Research how to do this on the web. 
#
# Vagrant’s own docs are best: https://www.vagrantup.com/docs/provisioning/file

# put your killer command for copying a file to the VM here.
# Remember that at this time the copying of this file serves no useful
# purposeful. It will soon.  Vagrant will copy the file into the
# /home/vagrant directory.
# Hint: your statement to copy users.sql should start like this:

 config.vm.provision "file", source: "/Users/Abdulrahman/module2vagrant", destination: "/home/vagrant"

end



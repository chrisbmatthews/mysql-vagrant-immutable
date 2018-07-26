# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  #Base box contains a mysql server
  config.vm.box = "cbmatthews/mysql-flyway"

  #We will remount /var/lib/mysql to a directory on my physical host
  config.vm.synced_folder "./mysql", "/var/lib/mysql", id: "mysql", owner: "mysql", group: "mysql",
    mount_options: ["dmode=775,fmode=664"]

  #After mounting, restart the mysql service so it will see the new /var/lib/mysql files
  config.vm.provision "shell", inline: "service mysql restart", run: "always"
end

# mysql-immutable Vagrant Example

This demonstrates a mysql vagrant box that preserves data on a vagrant destroy + vagrant up.

See the full youtube video here:

Basically, to reproduce this, the first time you run, comment out the config.vm.synced_folder setting in the Vagrantfile.

Run:

    $ vagrant up
    $ vagrant ssh
    $ sudo bash
    $ cp -R /var/lib/mysql /vagrant
    $ exit
    $ exit

Then uncomment the config.vm.synced_folder setting in the Vagrantfile and run:

    $ vagrant reload

This should force all data form the mysql service to be read and written to a mysql/ directory in your vagrant project directory.

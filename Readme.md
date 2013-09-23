# Package Varnish with VMODs


## Requirements:

  - [Vagrant - Download](http://downloads.vagrantup.com/)
  - Vagrant-cachier

      `vagrant plugin install vagrant-cachier`

  - Ubuntu 12.04 box

      `vagrant box add precise64 http://files.vagrantup.com/precise64.box`

## Installation
    $ git clone https://github.com/mindreframer/vagrant-varnish-vmods-builder.git

    $ cd vagrant-varnish-vmods-builder

    # will install vagrant plugins
    $ sh/update-plugins

    $ vagrant up box1
    $ vagrant ssh box1 -c "sudo /vagrant/sh/install-varnish.sh"

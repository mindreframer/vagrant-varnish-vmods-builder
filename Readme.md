# Package Varnish with [VMODs](https://www.varnish-cache.org/vmods)


## What is this?
  This script will create a Debian/Ubuntu package for [Varnish Cache Server](https://www.varnish-cache.org/) with following VMODs compiled in:
<!-- VMODS_LIST_START -->

<!-- VMODS_LIST_END -->


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


## Testing on a clean system

    $ vagrant up box2
    $ vagrant ssh box2
    ## on the box2 system
    $ apt-get install gdebi-core
    $ gdebi -n /vagrant/pkg/varnish-3.0.4.ubuntu.12.04_amd64.deb
    # get the list of installed VMODs
    $ ls -la /usr/local/lib/varnish/vmods


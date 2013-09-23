# Package Varnish with [VMODs](https://www.varnish-cache.org/vmods)


## What is this?
  This script will create a Debian/Ubuntu package for [Varnish Cache Server](https://www.varnish-cache.org/) with following VMODs compiled in:
<!-- VMODS_LIST_START -->
    *** GENERATED BY sh/update_readme.rb *** 

    statsd: 
       - https://github.com/jib/libvmod-statsd.git
    timers: 
       - https://github.com/jib/libvmod-timers.git
    curl: 
       - https://github.com/varnish/libvmod-curl.git
    ipcast: 
       - https://github.com/lkarsten/libvmod-ipcast.git
    throttle: 
       - https://github.com/nand2/libvmod-throttle.git
    var: 
       - https://github.com/varnish/libvmod-var.git
    memcached: 
       - https://github.com/sodabrew/libvmod-memcached.git
    digest: 
       - https://github.com/varnish/libvmod-digest.git
    shield: 
       - https://github.com/varnish/libvmod-shield.git
    threescale: 
       - https://github.com/3scale/libvmod-3scale.git
    cookie: 
       - https://github.com/lkarsten/libvmod-cookie.git
    urlcode: 
       - https://github.com/fastly/libvmod-urlcode.git
    timeutils: 
       - https://github.com/jthomerson/libvmod-timeutils.git
    dgram: 
       - https://github.com/mmb/vmod_dgram.git
    parsereq: 
       - https://github.com/xcir/libvmod-parsereq.git
    header: 
       - https://github.com/varnish/libvmod-header.git
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


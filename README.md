Vagrant + Chef-solo + Hadoop
============================

*0x00C0FFEE Donetsk September 2013*

Epigraph
--------

[![movie](http://proc.com.ua/uploads/posts/2011-01/thumbs/1295298889_shof-2.jpg)](http://proc.com.ua/films/69687-shofyor-ponevole-1958-dvdrip.html)


"Redis client" demo
-------------------

[Vagrant Downloads](http://downloads.vagrantup.com)

```bash
dpkg --get-selections  | grep vagrant
```

```bash
cd ~/projects/demo && ruby redis_client.rb
vagrant init
```

```ruby
config.vm.box = "precise64"
config.vm.box_url = "http://files.vagrantup.com/precise64.box"
```

```bash
vagrant up
vagrant ssh
```

[Redis Quick Start](http://redis.io/topics/quickstart)

```ruby
config.vm.network :forwarded_port, guest: 6379, host: 6379
```

```bash
vagrant reload
```

Vagrant
-------

[![Vagrant](http://www.hashicorp.com/images/blog/a-new-look-for-vagrant/logo_wide-cab47086.png)](http://www.hashicorp.com/blog/a-new-look-for-vagrant.html )


* [Vagrant boxes](http://www.vagrantbox.es/)
* [Sinced folders](http://docs.vagrantup.com/v2/synced-folders/)
* [Private network](http://docs.vagrantup.com/v2/networking/private_network.html)
* ["multi-machine" environment](http://docs.vagrantup.com/v2/multi-machine/index.html)
* [Configuration](http://docs.vagrantup.com/v2/providers/configuration.html)

Chef-solo
---------

[![Chef-solo](http://docs.opscode.com/_static/opscode_chef_html_logo.png)](http://www.hashicorp.com/blog/a-new-look-for-vagrant.html )

[Chef Solo provisioning for Vagrant](http://docs.vagrantup.com/v2/provisioning/chef_solo.html)

"Hadoop" demo
-------------

```bash
vagrant destroy
rm Vagrant && vagrant init
```

```ruby
config.vm.box = "precise64"
config.vm.box_url = "http://files.vagrantup.com/precise64.box"
config.vm.network :forwarded_port, guest: 50070, host: 50070
config.vm.network :forwarded_port, guest: 50075, host: 50075
    chef.add_recipe "apt"
    chef.add_recipe "java"
    chef.add_recipe "pseudo_distributed_cdh4"
```

[Chef cookbooks](http://community.opscode.com/)

```bash
mkdir cookbooks
vagrant up
```

[Hadoop GUI](http://localhost:50075)

Chef-solo #2
------------

[Chef-solo page](http://docs.opscode.com/chef_solo.html)

Resource examples:

* [Simple example](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/09067fdd0dd3aca43ca038620771d1f81b16be88/recipes/default.rb#L6-9)
* [Imperative ruby code](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/09067fdd0dd3aca43ca038620771d1f81b16be88/recipes/default.rb#L32-43)
* [Idempotency](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/09067fdd0dd3aca43ca038620771d1f81b16be88/recipes/default.rb#L45-50)
* [Resource as desirable state](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/09067fdd0dd3aca43ca038620771d1f81b16be88/recipes/default.rb#L81-85)
* [List of resources](http://docs.opscode.com/resource.html#resources)

Custom Lightweight Resources:

* [Problem](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/c1325a31db625c80fd5850c505ab6d4fb591dd11/recipes/default.rb#L61-116)
* [Provider](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/master/providers/hdfs_dir.rb)
* [Resource](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/master/resources/hdfs_dir.rb) 
* [Usage](https://github.com/MitinPavel/pseudo_distributed_cdh4/blob/master/recipes/default.rb#L58-67)

Questions
---------

[![Questioins](http://pics.livejournal.com/sovietdetstvo/pic/000qfxwz)](http://sovietdetstvo.livejournal.com/132921.html)

Pavel Mitin:

* [@map_and_filter](https://twitter.com/map_and_filter)
* [http://novembermeeting.blogspot.com/](http://novembermeeting.blogspot.com/)

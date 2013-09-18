Vagrant + Chef-solo + Hadoop
============================

*0x00C0FFEE Donetsk September 2013*

Epigraph
--------

[![movie](http://proc.com.ua/uploads/posts/2011-01/thumbs/1295298889_shof-2.jpg)](http://proc.com.ua/films/69687-shofyor-ponevole-1958-dvdrip.html)

Vagrant
-------


[![Vagrant](http://www.hashicorp.com/images/blog/a-new-look-for-vagrant/logo_wide-cab47086.png)](http://www.hashicorp.com/blog/a-new-look-for-vagrant.html )

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

First slide set
---------------

[![Chef-solo](http://docs.opscode.com/_static/opscode_chef_html_logo.png)](http://www.hashicorp.com/blog/a-new-look-for-vagrant.html )

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

Questions
---------

[![Questioins](http://pics.livejournal.com/sovietdetstvo/pic/000qfxwz)](http://sovietdetstvo.livejournal.com/132921.html)


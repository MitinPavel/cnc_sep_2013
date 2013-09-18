Vagrant + Chef-solo + Hadoop

============================

*Presentation on C&C Donetsk September 2013*

Epigraph
--------

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

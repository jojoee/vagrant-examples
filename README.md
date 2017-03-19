# vagrant-examples

- Vagrant: Manages VM software
- Vagrantfile: virtual machine configuration

## Getting started

1. Install VirtualBox
2. Install [Vagrant](https://www.vagrantup.com/), after install Vagrant, it'll update our hosts file
3. Go to directory: `cd baked-lamp`
4. Start: `vagrant up`

## CLI

```
Basic
$ vagrant help
$ vagrant -v
$ vagrant box list
$ vagrant box update
$ vagrant init [box-name]
$ vagrant init ubuntu/trusty64
$ vagrant up

To access
$ vagrant ssh

Plugin
$ vagrant plugin list
# vagrant plugin update
$ vagrant plugin install <plugin-name>
$ vagrant plugin install vagrant-vbguest

While running
$ vagrant provision
$ vagrant suspend...........pause
$ vagrant halt..............power off VM
$ vagrant destroy...........stop and remove VM
$ vagrant status
$ vagrant reload

Box
$ vagrant box add <box-name> [box-path]
$ vagrant box add ubuntu/trusty64
$ vagrant box add laravel/homestead
$ vagrant box add debian/jessie64
$ vagrant box add centos/7
$ vagrant box add miya0001/vccw
$ vagrant remove <box-name>
```

## Provisioning

Baked: make it from scratch

```
$ vagrant up
$ vagrant ssh

Inside VM
$ sudo yum update -y
$ sudo yum install -y nano git unzip screen
$ sudo yum install -y httpd httpd-devel httpd-tools
$ sudo yum install -y php php-cli php-common php-devel php-mysql
$ sudo chkconfig --add httpd
$ sudo chkconfig httpd on
$ cd /var/www
$ sudo rm -rf html
$ sudo ln -s /vagrant /var/www/html
$ sudo service httpd restart
$ sudo yum install -y mysql mysql-server mysql-devel
$ sudo chkconfig --add mysqld
$ sudo chkconfig mysqld on
$ sudo service mysqld start
$ mysql -u root -e "CREATE DATABASE IF NOT EXISTS jojoee_test";
$ mysql -u root -e "SHOW DATABASES";
$ exit

Export to box
$ vagrant status
$ vagrant package --output baked-lamp.box
$ vagrant box add "jojoee/baked-lamp" baked-lamp.box

Test
$ cd baked-lamp-test
$ vagrant up

http://localhost:8080/
http://localhost:8080/index.php
http://localhost:8081/
http://localhost:8081/index.php
```

## Update

- [x] Work with database (e.g. MySQL)
- [ ] Plugin

## Reference

- [Vagrant](https://www.vagrantup.com/)
- [Vagrant documentation](https://www.vagrantup.com/docs/)
- [Vagrantfile](https://www.vagrantup.com/docs/vagrantfile/)
- Vagrant Box: [Discover Vagrant Boxes](https://atlas.hashicorp.com/boxes/search), [Vagrantbox.es](http://www.vagrantbox.es/)
- [Available Vagrant Plugins](https://github.com/mitchellh/vagrant/wiki/Available-Vagrant-Plugins)

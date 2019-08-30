# Creating a disposable development environment with Virtualbox, Vagrant and Ansible

## Vagrant

This tool works together with Virtualbox and makes it possible to easily create, start, provision, stop and destroy virtual machines and is often used to create disposable development environments.  Vagrant runs on AWS, Docker and VMware.

## Installation

We will first provision one centos master machine in Virtual box. You can download the image [here](http://isoredirect.centos.org/centos/7/isos/x86_64/CentOS-7-x86_64-DVD-1810.iso)

Once the basic installation is done install ansible using the command

```bash
$ sudo yum install ansible
```

Install VirtualBox 5.1 on CentOS

First install VirtualBox dependencies.

```bash
$ yum -y install gcc dkms make qt libgomp patch 
$ yum -y install kernel-headers kernel-devel binutils glibc-headers glibc-devel font-forge
```

Next add VirtualBox repository.

```bash
$ cd /etc/yum.repo.d/
$ wget http://download.virtualbox.org/virtualbox/rpm/rhel/virtualbox.repo
```

Now install and build kernel module.
```bash
$ yum install -y VirtualBox-5.1
$ /sbin/rcvboxdrv setup
```
Next, Download and install the latest version of Vagrant

```bash
$ sudo yum -y install https://releases.hashicorp.com/vagrant/1.9.6/vagrant_1.9.6_x86_64.rpm
```
Create a directory where vagrant will be installed.

```bash
$ mkdir ~/vagrant-home 
$ cd ~/vagrant-home 
```

Install the distro or operating system you want on the host. 

```bash
----------- Installing Ubuntu -----------
$ vagrant init ubuntu/xenial64

----------- Installing CentOS -----------
$ vagrant init centos/7
```

A file called Vagrantfile will be created in your current directory. This file contains configuration settings for your virtual machines.

[![vagrantfile.png](https://i.postimg.cc/1tNGbBFw/vagrantfile.png)](https://postimg.cc/dkwZy84V)

Boot up the host server.

```bash
$ vagrant up
```

## References

1. Creating a disposable development environment with Virtualbox, Vagrant and Ansible: [https://ronaldvaneede.me/setting-up-a-disposable-development-environment-with-virtualbox-vagrant-and-ansible-127816cd0479](https://ronaldvaneede.me/setting-up-a-disposable-development-environment-with-virtualbox-vagrant-and-ansible-127816cd0479 "Creating a disposable development environment with Virtualbox, Vagrant and Ansible")

2. How to Install Vagrant on CentOS 7: [https://www.tecmint.com/how-to-install-vagrant-on-centos-7/](https://www.tecmint.com/how-to-install-vagrant-on-centos-7/ "How to Install Vagrant on CentOS 7")

3. Ansible & Vagrant - A Basic Playbook for Vagrant & CentOS 7: [https://www.youtube.com/watch?v=MQ1Y3Uz2RQ0](https://www.youtube.com/watch?v=MQ1Y3Uz2RQ0 "Ansible & Vagrant - A Basic Playbook for Vagrant & CentOS 7")
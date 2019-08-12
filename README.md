# AnsibleBigDataAutomation

This repository contains scripts for automated big data cluster/Data Science cluster deployments using Ansible.

## What is Ansible?

It is an automation language that can be used to automate IT Infrastructure deployments. Ansible models IT infrastructure by describing how all of the systems inter-relate, rather than just managing one system at a time.

It uses no agents and no additional custom security infrastructure, so it's easy to deploy - and most importantly, it uses a very simple language (YAML, in the form of Ansible Playbooks) that allows users to describe automation jobs in a way that approaches plain English.

Ansible Tower is a framework for controlling,securing and managing ansible automation with a UI and RESTful API

## Why Ansible ?

#### 1. It is simple.

* Human readable automation. 
* No special coding skills required.
* Tasks are executed in order.
* Get productivity quicker.

#### 2. It is powerful.

* Application deployment.
* Configuration Management.
* Workflow orchestration.
* Orchestrate the application lifecycle.

#### 3. It is agentless.

* Agentless architecture.
* Uses OpenSSH and WinRM.
* No agents to exploit or update.
* More efficient and secure.

#### 4. It is cross platform.

* Agentless support for all major OS, varients, physical, virtual, cloud and network.

#### 5. It works with existing toolkits

* Homogenize existing environments by leveraging current toolsets and update mechanisms. 

#### 6. It comes bundled with 450+ modules

* Cloud
* Container
* Database
* Files
* Messaging
* Monitoring
* Network
* Notifications
* Packaging
* Source Control
* System
* Testing
* Utilities
* Web Infrastructure

##### Commonly used modules
* apt/yum
* copy
* file
* get_url
* git
* ping
* debug
* service
* synchronize
* template
* url
* user
* wait_for
* assert


For More information on modules, [click here](https://docs.ansible.com/ansible/latest/modules/modules_by_category.html "doc.ansible.com")

## Ansible Essentials

1. Inventory

    Inventory is a collection of hosts (nodes) against which the Ansible can work with. These includes: 

    * Hosts.
    * Groups sources.
    * Inventory-specific data or variables.
    * Static or dynamic source.

Static Inventory example

[![staticinventoryexample.png](https://i.postimg.cc/pdNtRZQL/staticinventoryexample.png)](https://postimg.cc/pmBSBK1w)

---

## Installing Ansible

```bash
# the most common and preferred way of installation
$ pip install ansible

# install the epel-release RPM if needed on CentOS , RHEL or Scientific Linux
$ sudo yum install ansible

# you will need the PPA repo configured
$ sudo apt-get install ansible 
```
We will be using the pip install method. 

> Note: To install python and pip on Windows10, [click here](https://github.com/apekshatrivedi/AnsibleBigDataAutomation/blob/AnsibleBasics/Python_and_pip_install_on_Windows10.md "Installing python and pip on Windows 10")

---

## AD - HOC Commands

```bash
# check all my inventory hosts are ready to be manged by Ansible
$ ansible all -m ping

# run the uptime command on all hosts in the web group
$ ansible web -m command -a "uptime"

# collect and display the discovered for the localhost
$ ansible localhost -m setup
```

The last command will yield the following results.

[![discovered.png](https://i.postimg.cc/nrpKq6vw/discovered.png)](https://postimg.cc/ftq0Nqqx)

## References

1. Introduction to Ansible tutorial: [https://www.ansible.com/resources/webinars-training/introduction-to-ansible](https://www.ansible.com/resources/webinars-training/introduction-to-ansible "Introduction-to-ansible")



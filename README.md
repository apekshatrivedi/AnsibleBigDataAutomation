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

    **Static Inventory example**

    ```properties
    [control]
    control ansible_host=10.42.0.2

    [web]
    node-1 ansible_host=10.42.0.6
    node-2 ansible_host=10.42.0.7
    node-3 ansible_host=10.42.0.8

    [haproxy]
    haproxy ansible_host=10.42.0.100

    [all:vars]
    ansible_user=vagrant
    ansible_ssh_private_key_file=~/.vagrant.d/insecure_private_key
    ```
2. Variables
   
   Ansible can work with metadata from various sources and manage their context in the form of variables.

   **Variable precedence**

   1. Extra vars
   2. Tasks vars (only for task)
   3. Block vars(only for tasks in the blocks)
   4. Role and include vars vars_files
   5. Play vars_files
   6. Play vars_prompt
   7. Play vars
   8. Set_facts
   9. Registered vars
   10. Host facts
   11. Playbook host_vars
   12. Playbook group_vars
   13. Inventory host_vars
   14. Inventory group_vars
   15. Inventory vars
   16. Role defaults
   
3. Tasks
   
   What a module does, It consists of arguments we pass to the module.

   Some examples:
   1. `file` : A directory should exist.
   2. `yum` : A package should be installed.
   3. `service` : A service should be running.
   4. `template` : Render a config file from a template.
   5. `get_url` : Fetch an archive file from a URL.
   6. `git` : Clone a source code repository.

    __Example tasks in a play__

    ```yaml
    tasks:
        - name: add cache dir
          file: 
            path: /opt/cache
            state: directory

        - name: install nginix
          service: 
            name: nginx
            state: restarted
        
    ```

    Normal tasks as shown above runs sequentially however ***Handler Tasks***, runs on notification. Handlers are special tasks that run at the end of a play if notified by another task. If a configuration file gets changed notify a service restart task it needs to run. 

    Example handler:

     ```yaml
    tasks:
        - name: add cache dir
          file: 
            path: /opt/cache
            state: directory
        - name: install nginix
          yum: 
            name: nginx
            state: latest
            notify: restart nginx
    
    handlers
        - name: restart nginix
          service: 
            name: nginx
            state: restarted
    ```

4. Plays and Playbooks

    Plays are ordered set of tasks to execute against host selections from your inventory. A playbook is a file containing one or more plays.

    **Playbook example**

    ```yaml
    - name : install and start apache
      hosts: web
      vars:
        http_port: 80
        max_clients: 200
      remote_user: root

      tasks:
      - name: install httpd
        yum: pkg=httpd state=latest
      - name: write the apache config file
        template: src=/srv/httpd.j2 dest=/etc/httpd.conf
      - name: start httpd
        service: name=httpd state=started
      
    ```
[Click here](https://github.com/apekshatrivedi/AnsibleBigDataAutomation/blob/AnsibleBasics/Example1/site.yaml "Example1") for more example playbook.

5. Roles

    Roles are a package of closely related Ansible content that can be shared more easily than plays alone.

    Playbook with roles.

    ```yaml
    - hosts: web
      roles: 
        - common
        - webservers
    ```
    Command to view create an ansible role structure
    `ansible-galaxy init rolename`

    
    
    By creating the roles directory structure ansible can identify if the YAMLS are tasks or handlers.

## Installing Ansible

```bash
# the most common and preferred way of installation
$ pip install ansible

# install the epel-release RPM if needed on CentOS , RHEL or Scientific Linux
$ sudo yum install ansible

# you will need the PPA repo configured
$ sudo apt-get install ansible 
```

> Note: Ansible can only manage Windows hosts. Ansible cannot run on a Windows host natively, though it can run under the [Windows Subsystem for Linux (WSL)](https://www.youtube.com/watch?v=vE5unuqIauE "WSL"). The Windows Subsystem for Linux is not supported by Ansible and should not be used for production systems. 

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

More ad-hoc commands are found [here](https://github.com/apekshatrivedi/AnsibleBigDataAutomation/blob/AnsibleBasics/ad-hoc_commands.md "ad-hoc commands")

## References

1. Introduction to Ansible tutorial: [https://www.ansible.com/resources/webinars-training/introduction-to-ansible](https://www.ansible.com/resources/webinars-training/introduction-to-ansible "Introduction-to-ansible")



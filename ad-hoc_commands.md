# Commonly used ad-hoc commands

Our hosts file is as follows

```bash
[webservers]
10.0.1.45
10.0.1.46
10.0.1.47

[dbservers]
10.0.1.48
```


## 1. Ping all the hosts. 

```bash
ansible all -i hosts -u vagrant -m ping
```

* `all` : All groups
* `-i` : Inventory
* `-u` : Users
* `-m` : Modules

Example output of the above command:

[![pingcommand.png](https://i.postimg.cc/j5BZpgYs/pingcommand.png)](https://postimg.cc/0MdYmCN3 "pingcommand.png")

## 2. Gathering facts.

```bash
ansible all -i hosts -u vagrant -m setup
```

## 3. Installing packages.

Here, we target only the web servers group.

```bash
ansible webservers -i hosts -u vagrant -m yum -a "name=httpd state=present" -b
```
* `-a` : Arguments
* `-b` : Escalate to root user.

> Note: Ansible is Idempotent i.e, If you try to run the command again. It will prompt that the package is already installed.

## 4. Remove/Rollback the package installed.

```bash
ansible webservers -i hosts -u vagrant -m yum -a "name=httpd state=absent" -b
```
## 5. Running the ansible playbook

Will run the [said](https://github.com/apekshatrivedi/AnsibleBigDataAutomation/blob/AnsibleBasics/Example1/site.yaml "Example1") playbook.

```bash
ansible-playbook -i hosts site.yaml
```
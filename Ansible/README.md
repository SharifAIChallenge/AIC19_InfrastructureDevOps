# Ansible Terms

* Controller Machine: the machine where Ansible is installed, responsible for running the provisioning on the servers you are managing
* Inventory: an INI file that contains information about the servers you are managing
* Playbook: the entry point for Ansible provisionings, where the automation is defined through tasks using YAML format
* Task: a block that defines a single procedure to be executed, e.g.: install a package
* Module: a module typically abstracts a system task, like dealing with packages or creating and changing files. Ansible has a multitude of built-in modules, but you can also create custom ones
* Role: a pre-defined way for organizing playbooks and other files in order to facilitate sharing and reusing portions of a provisioning
* Play: a provisioning executed from start to finish is called a play
* Facts: global variables containing information about the system, like network interfaces or operating system
* Handlers: used to trigger service status changes, like restarting or stopping a service


## ansible master(the machine that is configuring all other machines with ansible) config:
ansible should be installed on the ansible master(it brings python as a dependency)

    sudo pacman -S ansible
    sudo apt install ansible
    brew install ansible
    
Ansible configurations are in `ansible.cfg` from repo which should be in the local directory.
cluster specs is listed in the inventory file which is by default in `/etc/ansible/hosts` but we have changed in to `hosts.yaml` in the config file.
Before running ansible you need to deploy your keys to the server. Make it simpler(?) [#todo](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#variables-and-vaults)

    ssh-copy-id <user>@<host> -p <port>

If you don't have a key in your system already you should run:

    ssh-keygen -t rsa -b 2048
    
AIC-2019 people can run 

`bash ansible/copy_keys.sh` to copy their keys

`bash ansible/test_all_servers.sh` to ssh to all servers one after another.(if you ^D you will get to the next server)

Verify that It's working:

    ansible all -m ping

## All hosts:

    sudo apt update
    sudo apt upgrade
    sudo apt install zsh git
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

## game_runner

## k8s master
```
create .kube
```
## k8s workers

    sudo apt install collectd collectd-utils
    sudo systemctl restart collectd.service

## Resources:
[digital ocean config management 101](https://www.digitalocean.com/community/tutorials/configuration-management-101-writing-ansible-playbooks)
[official ansible docs](https://docs.ansible.com/ansible/latest/)

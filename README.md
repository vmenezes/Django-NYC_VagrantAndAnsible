# Django-NYC_VagrantAndAnsible

A last minute talk about Vagrant + Ansible for development/deployment of Django projects

## This is still under development...

Tested on:

- Ubuntu 18.04
- VirtualBox 5.2.18
- Vagrant 2.0.2


## Vagrant commands

```
vagrant up
vagrant halt
vagrant destroy
vagrant provision
vagrant ssh
```

## Ansible commands

```
ansible [group_name_from_inventory] -i [inventory_folder] -a [any_linux_command]
ansible all -i deploy/staging -a 'df -h'
ansible-playbook deploy/playbook.yml -i deploy/staging --ask-vault-pass

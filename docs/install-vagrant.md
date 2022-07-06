# Install Vagrant

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts vagrant.yml
```

This will Vagrant from official channel.

## Manually

```shell
sudo apt install vagrant
```

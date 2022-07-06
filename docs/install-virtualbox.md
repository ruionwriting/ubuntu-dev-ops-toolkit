# Install VirtualBox

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts virtualbox.yml
```

This will VirtualBox from official channel.

## Manually

```shell
sudo apt install virtualbox
```

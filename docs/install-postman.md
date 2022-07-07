# Install Postman

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts postman.yml
```

This will Postman via Snap.

## Manually

> I've pretty much implemented these using Ansible. Its mostly educational.

```shell
sudo snap install postman
```

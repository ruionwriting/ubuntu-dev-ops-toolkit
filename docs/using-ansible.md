# Using Ansible

> **Note**
> This is work in progress as I learn Ansible or I get stuck at something. I'm not an Ansible expert neither I use it that offten to claim that I know Ansible.

## Debug

To debug a playbook run use `ANSIBLE_DEBUG` variable to enable debug:

```shell
ANSIBLE_DEBUG=1 ansible-playbook -K -i hosts vscode.yml
```

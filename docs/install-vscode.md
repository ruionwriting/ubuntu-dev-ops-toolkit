# Install Visual Studio Code

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts vscode.yml
```

This will Visual Studio Code from official channel.

## Manually

> I've pretty much implemented these using Ansible. Its mostly educational:

* [https://linuxhint.com/install_use_vs_code_ubuntu]()
* [https://docs.microsoft.com/en-us/windows-server/administration/linux-package-repository-for-microsoft-software#configuring-the-repositories]()

# Install Ansible

Refresh the system's package index:

```shell
sudo apt update
```

Install Ansible:

```
sudo apt install ansible
```

Check installed version:

```shell
$ ansible --version
ansible 2.10.8
  config file = None
  configured module search path = ['/home/rui/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.10.4 (main, Apr  2 2022, 09:04:19) [GCC 11.2.0]
```

> **Note**
> Your `$HOME` should have your user. This `rui` is my case.

# Ubuntu on VWware

Ubuntu on VMware (Workstation/Fusion Pro) for multi-purpose development and automation tasks.

## Minimal setup

1. [Create new virtual machine](./docs/create-new-virtual-machine.md)
1. [Install operating system](./docs/install-operating-system.md)
1. [Post-install operating system](./docs//post-install-operating-system.md)
1. [Install Ansible](./docs/install-ansible.md)

> **Note**
> From this point you have a standard Ubuntu 64-bit VM that is up-to-date and that tou can now install any (if not all) common DevOps utilities and toolchains that can run on Ubuntu. Take a snaphot at every stage (or at any time for that matter) and you have a stable and predictable environment to use.

## Utilities and toolchains

### Containerisation and Virtualisation

* [Docker and Docker Compose](./docs/install-docker.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts docker.yml)` inside your VM


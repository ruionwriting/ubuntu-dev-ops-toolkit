# Ubuntu DevOps Toolkit

---

[Ubuntu DevOps Toolkit](https://github.com/ruionwriting/ubuntu-dev-ops-toolkit) (UDOT) is a highly opinionated Ubuntu all-purpose DevOps environment setup that can run bare-metal or in a virtual machine. From general code development, IaC, containerization, virtualization and testing tools, I've got you covered.

Why? Read about the [motivation](#motivation) for this project.

**In this document**:

- [Current Status](#current-status)
- [Minimal setup](#minimal-setup)
- [Utilities and toolchains](#utilities-and-toolchains)
  - [Development tools/IDEs](#development-toolsides)
  - [Testing tools](#testing-tools)
  - [Language/runtimes](#languageruntimes)
  - [Containerization and virtualization](#containerization-and-virtualization)
  - [Infrastructure as Code (IaC)](#infrastructure-as-code-iac)
- [Motivation](#motivation)
- [License](#license)

---

## Current Status

Ubuntu DevOps Toolkit is **currently tested with bare-metal or virtualized using VMware Workstation Pro and VMware Fusion Pro**, so Linux, macOS and Windows hosts can be used. I do plan to expand to and cover VirtualBox, VWware Workstation Pro and VMware Fusion Player.

Feature|Bare-metal|VMware Workstation Pro|VMware Fusion Pro|VWware Workstation Player|VMware Fusion Player|VirtualBox
-|:-:|:-:|:-:|:-:|:-:|:-:
Guest OS|_N/A_|Linux or Windows|macOS|Linux or Windows|macOS|Linux, macOS or Windows
Performance|best|very good|very good|_TBC_|_TBC_|good, for most things
Snapshots|_N/A_|&#10003;|&#10003;|_N/A_|_N/A_|&#10003;
Limitations\*|none|none|none|_TBC_|_TBC_|_TBC_

(\*) UDOT offers a best-effort when it comes to testing, document and automation installation of the various tools but in some cases licensing or environment constraints may limit some functionality. I'll do my best to capture those here.

## Minimal setup

1. [Create new virtual machine](./docs/create-new-virtual-machine.md). Skip if using bare-metal.

   > **Note**
   > Refer to [Current Status](#current-status) to see what options currently covered.

1. [Install operating system](./docs/install-operating-system.md)
1. [Post-install operating system](./docs//post-install-operating-system.md)
1. [Install Ansible](./docs/install-ansible.md)

> **Note**
> From this point you have a standard Ubuntu 64-bit VM that is up-to-date and that tou can now install any (if not all) common DevOps utilities and toolchains that can run on Ubuntu. Take a snapshot at every stage (or at any time for that matter) and you have a stable and predictable environment to use.

## Utilities and toolchains

> **Note**
> All instructed `ansible-playbook` commands in this document assume that the minimal setup is complete and you run the commands inside your VM.

### Development tools/IDEs

- [Visual Studio Code](./docs/install-vscode.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts vscode.yml)`

### Testing tools

- MockServer `WIP`
- Newman `WIP` (CLI runner for Postman collections)
- newman-reporter-htmlextra (HTML reporter for Newman)
- Postman `WIP`

### Language/runtimes

- .NET `WIP`
- Go `WIP`
- Java `WIP`
- NodeJS (using nvm) `WIP`
- Python `WIP`
- Ruby (using rbenv) `WIP`
- [Rust](./docs/install-rust.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts rust.yml)`

### Containerization and virtualization

- [Docker and Docker Compose](./docs/install-docker.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts docker.yml)`
- [VirtualBox](.docs/../docs/install-virtualbox.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts virtualbox.yml)`
- [Vagrant](.docs/../docs/install-vagrant.md) or simply run `(cd playbooks && ansible-playbook -K -i hosts vagrant.yml)`

### Infrastructure as Code (IaC)

- [Ansible](./docs/install-ansible.md) is part of our minimal setup. Read [Using Ansible](./docs/using-ansible.md) for some crude usage/troubleshooting notes
- Chef. `WIP`
- Terraform (bare). `WIP`
- Terraform (using tfenv). `WIP`
- Terragrunt (bare). `WIP`
- Terragrunt (using tgenv). `WIP`

## Motivation

> **Note**
> **I'm not affiliated with or sponsored by VMware.**

As an engineer focused on building and maintaining tools that help engineers to be effective on their daily work I found that one of the biggest challenges is the amount of variation that exists across the various platforms. I've found Ubuntu to be a very well-round desktop solution that can replace most of my needs in a consistent manner.

I wanted a repeatable approach to work that can run on any host OS. Key aspects:

- A single thing/process to maintain and evolve
- Easy to automate using Ansible (or Bash or whatever you fancy)
- Checkout a single repo and use provided docs, scripts and playbooks and have peace of mind that I can get into a working state quickly
- Something that works for personal and corporate situations
- When using virtualization having the ability to snapshot at any moment and to enable to rollback in case I get in trouble - I want to be productive

Why I use VMware?

I've simply burned too many cycles with VirtualBox and other free solutions. Don't take me wrong there are many good options around there but I favour, for productivity, easy to use and adopt. I've learned over the years to appreciate VMware stability and I don't mind paying for a license of a software that just works and is predictable.

---

## License

This work is licensed under Apache-2.0. See the [LICENSE.txt](LICENSE.txt) file for more information.

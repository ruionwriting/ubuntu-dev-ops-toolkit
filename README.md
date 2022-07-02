# Highly opinionated Ubuntu all-purpose DevOps running on VWware

Ubuntu on VMware (Workstation/Fusion Pro) for multi-purpose development and automation tasks.

## Motivation

> **TL;DR**;
> I'm a macOS, Windows and Linux user. As an engineer focused on building and maintaining tools that help engineers to be effective on their daily work I found that one of the biggests challenge is the amount of variantion that exists across the various platoforms. I've found Ubuntu to be a very well-round desktop solution that can replace most of my needs in a consistent manner.

* As a macOS user, most of my full-time job, I find my-self fighting some common wars:
  * Anything that depends on XCode like `gcc`, `cc`, `clang`, etc is subject to get broken frequently on major macOS updates, it's a PITA
  * Docker Desktop in macOS not only is slow but also it's kind not behave like "real" Docker, I don't care about shiny UI
* As a Linux user, my personal choice for all things development (mostly study/exploring) outside work, I finds things a lot more flexible and fast but:
  * I'm not a Linux top expert and once in a while I just screw-up big time and can break my workflows, I need to have an environment that I can rebuild fast in a repeatable fashion
* As a Windows user - it works great for me in things link general use, gamming, audio/video production - I find it very hard to work for engineering tasks:
  * Hyper-V and Docker Desktop, and VirtualBox (yeah because I need it sometimes)
  * WSL2 can me a mess to get it right and to work all the time
  * Version managers for Ruby, NodeJS, Python, etc are a pain or non-existing
  * I know PowerShell is getting better but why to I need to ignore all the POSIX stuff I know
* I want a repeatable approach to work that can run on any host OS:
  * A single thing/process to maintain and evolve
  * Easy to automate using Ansible (or Bash or whatever you fancy)
  * Checkout this repo and use provides docs, scripts and playbooks and have peace of mind that I can get into a working state quickly
  * Something that works for personal and corporate situations
  * Having the hability to snaphot at any moment and to enable to rollback in case I get in trouble - I want to be productive

Why VMware?

I've simply burn too many cycles with VirtualBox, don't take me wrong it's a nice bit of software for most virtualization needs but there are others around. I've learned over the years to appreaciate VMware stability and I don't mind to pay for a license of software that just works and is predictable. **I'm not affiliate with or sponsored by VMware**.

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


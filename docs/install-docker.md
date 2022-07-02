# Install Docker and Docker Compose

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts docker.yml

```

This will:

* Install Docker CE adding sources list so it's easy to upgrade. See [Post-install operating system](./post-install-operating-system.md)
* Add your user to the `docker` group so you can run `docker` commands without `sudo`
* Download and install specified Docker Compose version defined by `docker_compose_version` variable (see _playbooks/docker.yml_)

## Manually

> I've pretty much implemented these using Ansible. Its mostly educational.

* [https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository](https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository)
* [https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04)

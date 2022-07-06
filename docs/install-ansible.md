# Install Ansible

> Ansible will be used all across to automate installing things onto our VM. This guide covers the basic for installation and to verify that Ansible is working for local. Ansible install will work as well for any other command Ansible workflow.

## Install

Refresh the system's package index:

```shell
sudo apt update
```

Install Ansible:

```shell
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

## Testing a local playbook

> **Note**
> I know very little about Ansible so make no assumptions about this process being the most correct. Certainly I'll come back to this and redo this guide/steps.

I've took inspiration from Adam Monsen [Ansible Hello World](https://github.com/meonkeys/ansible-hello-world) and Alexey Zalesny [How to run an Ansible playbook locally gist](https://gist.github.com/alces/caa3e7e5f46f9595f715f0f55eef65c1).

1. Create a _playbooks_ folder:

   ```shell
   mkdir playbooks
   ```

2. Move to the new folder and create _hosts_ file with the following content:

   ```ini
   [test]
   rui-virtual-machine ansible_connection=local

   ```

   > **Note**
   > This is my example hostname `rui-virtual-machine` change it accordingly to match your VM hostname.

3. Now create a file named _hello.yml_ with the following content:

   ```yaml
   - hosts: rui-virtual-machine
     tasks:
       # see https://docs.ansible.com/ansible/ping_module.html
       - name: test connection
         ping:

   ```

4. Let's run the playbook:

   ```shell
   $ ansible-playbook -i hosts hello.yml

   PLAY [rui-virtual-machine] **************************************************************************

   TASK [Gathering Facts] ******************************************************************************
   ok: [rui-virtual-machine]

   TASK [test connection] ******************************************************************************
   ok: [rui-virtual-machine]

   PLAY RECAP ******************************************************************************************
   rui-virtual-machine        : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

   ```

   Nice, we can run Ansible playbooks. We could also run the `ping` module directly and see more details about the hosts, in this case our guest VM:

   ```shell
   $ ansible all -i hosts -m ping
   rui-virtual-machine | SUCCESS => {
       "ansible_facts": {
           "discovered_interpreter_python": "/usr/bin/python3"
       },
       "changed": false,
       "ping": "pong"
   }

   ```

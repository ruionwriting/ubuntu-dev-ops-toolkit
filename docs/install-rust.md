# Install Rust

## Using Ansible

Assuming you have followed [Install Ansible](install-ansible.md) then is as simple as (from the _playbooks_ folder) running:

```shell
ansible-playbook -K -i hosts rust.yml
```

This will Rust and Cargo.

## Manually

[Which installer should you use?](https://forge.rust-lang.org/infra/other-installation-methods.html#which-installer-should-you-use)

```shell
curl https://sh.rustup.rs -sSf | sh
```

Uninstall Rust:

```shell
rustup self uninstall
```

Add `source $HOME/.cargo/env` to your shell configuration in case the installer fails to do so.

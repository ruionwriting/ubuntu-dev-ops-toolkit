# Post-install operating system

> **Note**
> For a good part of configuration the GUI can be used but I'll favor the use of a terminal. For Kubuntu we use Konsole.
>
> VMware Tools might need to be installed so we can have clipboard sharing, free stretch of the screen, etc to work as desired. For Kubuntu at least the installation is advised after upgrading the operating system.

- [Ensure the operating system is up-to-date](#ensure-the-operating-system-is-up-to-date)
- [Install VMware Tools](#install-vmware-tools)
- [Install common tools](#install-common-tools)
- [Regular maintenance](#regular-maintenance)
  - [Update the operating system](#update-the-operating-system)
  - [Remove orphan packages](#remove-orphan-packages)
- [Troubleshooting](#troubleshooting)
  - [VMware Guest](#vmware-guest)

---

## Ensure the operating system is up-to-date

```shell
sudo apt update && sudo apt upgrade
```

Snap packages:

```shell
sudo snap refresh
```

---

## Install VMware Tools

```shell
sudo apt install open-vm-tools-desktop
```

Now reboot the VM:

```shell
sudo reboot
```

Now when maximizing the window or adjusting it's size we have the Ubuntu desktop to adapt the resolution. And bi-directional clipboard is expected to work as well.

---

## Install common tools

```shell
sudo apt install -y \
     curl \
     vim
```

---

## Regular maintenance

### Update the operating system

```shell
sudo apt update && sudo apt upgrade
```

### Remove orphan packages

```shell
sudo apt autoremove
```

---

## Troubleshooting

### VMware Guest

<details>
  <summary>Shared folder does not mount automatically at boot</summary>

  &nbsp;
  It is a [known issue](https://communities.vmware.com/t5/VMware-Workstation-Player/Shared-folder-not-working-W11-host-Ubuntu-22-04-guest-Open-VM/td-p/2905917) that impacts Linux guests.

   Using `sudo` add the following line to _/etc/fstab_:

   ```shell
   vmhgfs-fuse /mnt/hgfs fuse defaults,allow_other 0 0
   ```

  After rebooting _/mnt/hgfs/_ should contain a folder mount for each shared folder.
</details>

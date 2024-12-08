# MS-01 "Feel the Thunder"

This Ansible playbook configures Thunderbolt networking support on the Minisforum MS-01 running Proxmox. It installs Intel microcode, enables Thunderbolt networking, and updates GRUB settings for Intel IOMMU and serial console support.

## Features

- Install Intel microcode from an external Debian package source
- Enable Thunderbolt networking by adding kernel modules and configuring systemd-networkd
- Install `lldpd` and `iperf` for network diagnostics
- Update `initramfs` and adjust `GRUB` parameters for improved device passthrough and Intel ME serial-over-LAN
- Reboot the system if changes are detected

## Requirements

- Minisforum MS-01 running Proxmox (Debian/Ubuntu-based)
- **Ansible** and **Git** installed on the target system
- SSH and sudo access for `ansible-pull` if not running as root

## Usage

Run `ansible-pull` **on the Proxmox host you want to configure**:

```bash
ansible-pull -U https://github.com/karubits/ms01-feel-the-thunder.git

# ansible-pct-ssh

Ansible connection plugin using ssh + pct

**Note:** The [community.proxmox](https://galaxy.ansible.com/ui/repo/published/community/proxmox/content/connection/proxmox_pct_remote/#notes)
collection has a `proxmox_pct_remote` connection plugin that can connect
Proxmox CTs using `pct` over SSH but can also put and fetch files which
this plugin **cannot**.

## Description

This plugin allows using Ansible to manage Proxmox containers without having to install
SSH servers in each CT.

The plugin connects to the host using SSH, then uses `pct` to enter the container.

## Configuration

Add to `ansible.cfg`:
```
[defaults]
connection_plugins = /path/to/connection_plugins/pct_ssh
```

Then, modify your `hosts` file to use the `pct_ssh` transport:
```
container ansible_host=proxmox_server ansible_connection=pct_ssh ct_id=container_id
```

## Fork

This is a fork from the [ansible-lxc-ssh](https://github.com/andreasscherbaum/ansible-lxc-ssh)
by Andreas Scherbaum.

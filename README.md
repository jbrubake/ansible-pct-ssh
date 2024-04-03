# ansible-pct-ssh

Ansible connection plugin using ssh + pct

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
container ansible_host=proxmox_server ansible_connection=pct_ssh lxc_host=container_id
```

`lxc_container=container` also works for setting the container name.

## Fork

This is a fork from the [ansible-lxc-ssh](https://github.com/andreasscherbaum/ansible-lxc-ssh)
by Andreas Scherbaum.

# Ansible Configuration Files

This repository contains the Ansible configuration files for my homelab. Managing the PVE cluster and all it's LXCs

## Initial Setup

### 1. initialize_pve_nodes.yml

This playbook readies the Proxmox VE nodes for Ansible management.
It installs the sudo package, which is required for Ansible to run commands with elevated privileges from a non-root user.
It adds the public key of the current machine to the authorized_keys file of the target nodes.
It creates the ansible user and adds it to the sudo group.

### 2. pve_install_proxmoxer.yml

This playbook installs the Proxmoxer Python library on the Ansible control machine.
Proxmoxer is a Python wrapper for the Proxmox VE API, and is required for further orchestration.

## Container Management

### 1. create_lxc.yml

This playbook creates a new LXC container on the Proxmox VE cluster.

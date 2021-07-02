# Big Data Stack

## Requirements

```bash
# install Ansible
sudo apt update
sudo apt install software-properties-common python3-pip
pip3 install ansible

# OPTIONAL: install sshpass if using ansible_password instead of ansible_ssh_private_key_file
sudo apt install sshpass

# install Ansible requirements
ansible-galaxy install -r requirements.yaml
```

## Configuration

- `inventory/group_vars/all.yaml`:
  - If `ansible_ssh_private_key_file` with correct ssh private key path
  - Else if `ansible_password` with correct ssh password
- `inventory/host_vars/n00.yaml`:
  - Edit `ansible_host` giving the correct IP or hostname
  - Edit `ansible_user` giving the correct username
- `inventory/hosts`:
  - Optionally add more hosts that needs to be added also under `inventory/host_vars` with correct name and configurations

## Run playbook

```bash
# Installation
ansible-playbook site.yaml [--tags [prerequisites, services]]

# Rollback
ansible-playbook site-rollback.yaml [--tags [uninstall]]
```

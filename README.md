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

Configure the inventory by changing username, password and ssh key/password under the `inventory` folder.

## Run playbook

```bash
# Installation
ansible-playbook site.yaml [--tags [prerequisites, services]]

# Rollback
ansible-playbook site-rollback.yaml [--tags [uninstall]]
```

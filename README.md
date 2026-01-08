# Ansible

## Install Ansible on Ubuntu system
```bash
sudo apt install ansible -y
```

## Test Connectivity (Ping Module)
```bash
ansible all --key-file ~/.ssh/ansible -i ./inventory -m ping
```

## List Hosts from Inventory
```bash
ansible all --list-hosts
```

## Gather System Facts (Display Output)
```bash
ansible all -m gather_facts
```

## Gather Facts and Save to Files
```bash
ansible all -m gather_facts --tree ./facts
jq . facts/<files> > facts/<files>.json
```

## Update APT Package Index
```bash
ansible all -m apt -a update_cache=true --become --ask-become-pass
```

## Install a Package with APT
```bash
ansible all -m apt -a name=iputils-ping --become
```
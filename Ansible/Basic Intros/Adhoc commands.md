# Ansible Adhoc Commands

## Ping All Hosts

ansible -i inventory.ini -m ping all

## Install OpenJDK on All Hosts

ansible -i inventory.ini -m shell -a "sudo snap install openjdk" all
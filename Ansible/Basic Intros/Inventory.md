```ini
# Sample Ansible Inventory File

# Define groups of hosts
[webservers]
webserver1.example.com
webserver2.example.com

[databases]
dbserver1.example.com
dbserver2.example.com

# Define variables for a group
[webservers:vars]
ansible_user=webadmin
ansible_ssh_private_key_file=/path/to/private/key

[databases:vars]
ansible_user=dbadmin
ansible_ssh_private_key_file=/path/to/private/key

# Define variables for a specific host
[webserver1.example.com]
ansible_host=192.168.1.10

[dbserver1.example.com]
ansible_host=192.168.1.20
```
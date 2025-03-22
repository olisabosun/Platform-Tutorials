# Writing Ansible Roles

Ansible roles help you organize and reuse your configuration by breaking it into smaller, reusable components. Here's how to write an Ansible role:

## 1. Create a Role Directory Structure
Use the `ansible-galaxy` command to create a role structure:
```bash
ansible-galaxy init <role_name>
```
This generates the following structure:
```
<role_name>/
├── defaults/
│   └── main.yml
├── files/
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
├── tests/
│   ├── inventory
│   └── test.yml
└── vars/
    └── main.yml
```

## 2. Define Tasks
Add tasks in `tasks/main.yml`:
```yaml
---
- name: Install Apache
  apt:
    name: apache2
    state: present
```

## 3. Add Variables
Define default variables in `defaults/main.yml`:
```yaml
---
apache_port: 80
```

## 4. Use Templates
Place Jinja2 templates in the `templates/` directory and reference them in tasks:
```yaml
- name: Deploy Apache config
  template:
    src: apache.conf.j2
    dest: /etc/apache2/apache2.conf
```

## 5. Add Handlers
Define handlers in `handlers/main.yml`:
```yaml
---
- name: Restart Apache
  service:
    name: apache2
    state: restarted
```

## 6. Use the Role in a Playbook
Reference the role in your playbook:
```yaml
---
- hosts: webservers
  roles:
    - <role_name>
```

## 7. Test the Role
Use the `tests/` directory to write test playbooks and validate your role.

By following this structure, you can create modular and reusable Ansible roles.
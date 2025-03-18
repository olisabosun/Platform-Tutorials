# How to Write an Ansible Playbook

Ansible playbooks are YAML files that define tasks to automate IT processes. Below is a guide to writing a basic playbook.

## Structure of a Playbook

1. **Define the Playbook**:
    - Start with a list of plays.
    - Each play targets a group of hosts.

2. **Specify Tasks**:
    - Tasks define the actions to perform on the hosts.

3. **Use Modules**:
    - Ansible modules perform specific tasks like installing packages or copying files.

## Example Playbook

```yaml
---
- name: Install and configure a web server
  hosts: webservers
  become: yes

  tasks:
     - name: Install Apache
        apt:
          name: apache2
          state: present
          update_cache: yes

     - name: Start Apache service
        service:
          name: apache2
          state: started
          enabled: yes

     - name: Copy index.html
        copy:
          src: /path/to/index.html
          dest: /var/www/html/index.html
```

## Steps to Execute the Playbook

1. Save the playbook as `playbook.yml`.
2. Run the playbook using the command:
    ```bash
    ansible-playbook -i inventory playbook.yml
    ```

## Best Practices

- Use descriptive names for tasks.
- Test playbooks in a staging environment.
- Use variables for reusable configurations.

For more details, refer to the [Ansible Documentation](https://docs.ansible.com/).
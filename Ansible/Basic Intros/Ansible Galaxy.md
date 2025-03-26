# How to Use Ansible Galaxy

Ansible Galaxy is a hub for finding, sharing, and downloading Ansible roles and collections. Here's a quick guide on how to use it:

## 1. Install a Role or Collection
To install a role or collection from Ansible Galaxy, use the following commands:
```bash
# Install a role
ansible-galaxy install <role_name>

# Install a collection
ansible-galaxy collection install <collection_name>
```

## 2. Search for Roles or Collections
You can search for roles or collections directly on the [Ansible Galaxy website](https://galaxy.ansible.com) or use the CLI:
```bash
# Search for a role
ansible-galaxy search <role_name>

# Search for a collection
ansible-galaxy collection search <collection_name>
```

## 3. Use Installed Roles or Collections
Once installed, you can use roles or collections in your playbooks:
```yaml
- hosts: all
    roles:
        - <role_name>

- hosts: all
    tasks:
        - name: Use a task from a collection
            ansible.builtin.debug:
                msg: "Hello, Galaxy!"
```

## 4. Create and Share Your Own
To create a new role or collection:
```bash
# Create a new role
ansible-galaxy init <role_name>

# Create a new collection
ansible-galaxy collection init <namespace.collection_name>
```
You can share your roles or collections by publishing them to Ansible Galaxy.

## 5. Manage Dependencies
Define dependencies in a `requirements.yml` file:
```yaml
roles:
    - name: geerlingguy.apache
collections:
    - name: ansible.posix
```
Install dependencies with:
```bash
ansible-galaxy install -r requirements.yml
```

For more details, visit the [official documentation](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html).

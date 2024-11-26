# Ansible Command-Line Reference Guide  

Welcome to this **Ansible command-line guide**! This document explores various aspects of the Ansible CLI to help you automate IT tasks effectively. Whether you're a beginner or an advanced user, this guide will provide you with the commands and descriptions you need to work with **Ansible**.  

---
## 📋 Prerequisites  

Before diving into the Ansible CLI, ensure:  
1. **Ansible is installed** on your system. (Check installation: `ansible --version`)  
2. You have a basic understanding of **Linux commands** and **SSH connectivity**.  
3. Managed nodes are set up and reachable over SSH from the control node.  

---

## 🚀 Common Ansible Commands  

Here are the core commands used in the Ansible CLI:  

### 1. `ansible`  

The `ansible` command allows you to execute **ad-hoc commands** on your managed nodes.  

#### Usage:  
```bash
ansible <pattern> -m <module_name> -a "<arguments>"
```

#### Example:
##### Ping all nodes in your inventory:
```bash
ansible all -m ping
```
##### Install a package on a managed node:
```bash
ansible web_servers -m yum -a "name=httpd state=present"
```
### 2. ansible-playbook
Use this command to execute playbooks that define complex tasks and configurations.
##### Usage:
```bash
ansible-playbook <playbook.yml>
```
##### Example:
Run a playbook to install and configure a web server:
```bash
ansible-playbook site.yml
```
### 3. ansible-inventory
View and manage your inventory file.
##### Usage:
```bash
ansible-inventory [options]
```
##### Example:
Display the inventory in a JSON format:
```bash
ansible-inventory --list
```
**Check inventory group names:**
```bash
ansible-inventory --graph
```
### 4. ansible-galaxy
Manage Ansible roles and collections from Ansible Galaxy.
##### Usage:
```bash
ansible-galaxy [command] [options]
```
##### Example:
Install a role:
```bash
ansible-galaxy install geerlingguy.apache
```
Create a new role directory structure:
```bash
ansible-galaxy init my_custom_role
```
### 5. ansible-doc
Display documentation for Ansible modules.
##### Usage:
```bash
ansible-doc <module_name>
```
##### Example:
View documentation for the ping module:
```bash
ansible-doc ping
```
### 6. ansible-config
View and manage Ansible configuration.
##### Usage:
``` bash
ansible-config <command> [options]
```
##### Example:
Display the current configuration:
```bash
ansible-config view
```
##### Verify Ansible configuration:
``` bash
ansible-config dump
```
## 📜 Detailed Examples
### Running Ad-Hoc Commands
##### Ping a single host:
``` bash
ansible <hostname> -m ping
```
##### Check disk space:
``` bash
ansible all -m shell -a "df -h"
```
##### Restart a service:
```bash
ansible web_servers -m service -a "name=httpd state=restarted"
```
##### Executing Playbooks
Basic playbook execution:
```bash
ansible-playbook playbook.yml
```
##### Run playbook in verbose mode:
```bash
ansible-playbook playbook.yml -v
```
##### Specify an inventory file:
``` bash
ansible-playbook playbook.yml -i custom_inventory
```
##### Managing Inventories
List all hosts in the inventory:
```bash
ansible all --list-hosts
```
##### Test connectivity with all hosts:
```bash
ansible all -m ping
```
##### Run a command on a specific group:
```bash
ansible db_servers -m shell -a "uptime"
```
##### Working with Ansible Roles
Install a role from Ansible Galaxy:
```bash
ansible-galaxy install username.rolename
```
##### Use a role in a playbook:
yaml format
```bash
- hosts: web_servers
  roles:
    - geerlingguy.apache
```
##### Debugging and Testing
Test a playbook with dry-run mode:
``` bash
ansible-playbook playbook.yml --check
```
##### Enable detailed logs:
``` bash
ansible-playbook playbook.yml -vvv
```
##### Log outputs to a file:
``` bash
ansible-playbook playbook.yml > log.txt
```
### 📚 Key Features of Ansible CLI
- **Ad-hoc Commands**: Perform quick tasks without writing a playbook.
- **Playbook Execution**: Automate complex workflows with YAML-based playbooks.
- **Inventory Management**: Organize nodes for scalability.
- **Extensibility with Roles**: Reuse modular configurations.
- **Configuration Management**: Customize behaviors via ansible.cfg.
### 🌟 Best Practices
- **Use Group Variables**: Simplify configurations by defining variables in group_vars/.
- **Always Test in Staging**: Verify playbooks in a non-production environment first.
- **Use Roles for Reusability**: Split playbooks into roles for maintainability.
- **Secure Sensitive Data**: Encrypt sensitive information with Ansible Vault.
**Let’s automate and simplify together!**  

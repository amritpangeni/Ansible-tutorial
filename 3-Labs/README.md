# Labs: Hands-on Ansible Exercises  

Welcome to the **Labs** section of our Ansible tutorial repository! This directory contains step-by-step, practical exercises designed to deepen your understanding of **Ansible automation**. Each lab is structured to teach specific skills, from basic configuration management to advanced use cases like roles, templates, and dynamic inventories.  

---

## 📋 Prerequisites  

Before you begin the labs, ensure you have the following in place:  
1. A fully configured **Ansible Lab Environment** (refer to the [1-LabSetup](./1-LabSetup/README.md)).  
2. Ansible installed and functioning on your **control node**.  
3. Passwordless SSH access from the control node to all managed nodes.  
4. Basic understanding of YAML and Ansible playbooks.  

---

## 📁 Lab Contents  

### Lab 1: **Basic Ping Test**  
- **Objective**: Verify connectivity between the control node and managed nodes.  
- **Skills Learned**:  
  - Using the `ping` module.  
  - Debugging connection issues.  
- **File**: [lab1_ping_test.yml](lab1_ping_test.yml)  

```yaml
- name: Lab 1 - Ping Test
  hosts: all
  tasks:
    - name: Ping managed nodes
      ping:

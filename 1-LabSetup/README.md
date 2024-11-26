# Ansible Tutorial: Lab Setup for Beginners  

Welcome to this step-by-step **Ansible tutorial**! This guide will help you set up a lab environment to learn and practice **Ansible configuration management**. By the end of this tutorial, you'll have a fully functional Ansible control node and managed nodes within a virtualized network.  

---

## 📋 Prerequisites  

Before we begin, ensure the following requirements are met:  
1. A system to create virtual machines (e.g., **VMware vCenter**, VirtualBox, AWS, or other platforms).  
2. Basic knowledge of networking and Linux commands.  
3. Ansible installed on the **control node** (we'll guide you through this).  

---

## 🖥️ Lab Architecture  

In this lab, we will create:  
- **1 Control Node**: Responsible for pushing configurations using Ansible.  
- **4 Managed Nodes**: Nodes where configurations will be applied.  

All virtual machines will be within the **same reachable network** to ensure Ansible can communicate over SSH.  

![Lab Architecture Diagram](#)(image.png)  
---

## ⚙️ Setting Up the Lab  

### Step 1: Create Virtual Machines  
1. Use **VMware vCenter** or any platform of your choice to create 5 virtual machines.  
   - **Control Node**: Install a Linux distribution (e.g., Ubuntu 20.04).  
   - **Managed Nodes**: Install the same or different Linux distributions based on your requirements.  
2. Assign static IP addresses or configure a DHCP server to ensure the nodes are within the same network or could be in different network but can communicate with each other. 
3. Verify connectivity by pinging each node from the control node.  

### Step 2: Configure the Control Node  
1. Install **Ansible** on the control node:  
   ```bash
   sudo apt update
   sudo apt install ansible -y

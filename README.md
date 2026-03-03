# 🛡️ SOC Lab Project

![Wazuh Logo](https://upload.wikimedia.org/wikipedia/commons/7/7d/Wazuh_logo.svg)

---

## Overview

This project demonstrates hands-on experience building a **Security Operations Center (SOC) lab**.  
The lab simulates a professional SOC environment for **monitoring, detecting, and analyzing cybersecurity events** using Wazuh across multiple operating systems.

**Objectives:**

- Monitor security events from multiple hosts  
- Practice SOC deployment and management  
- Simulate attacks and incident response in a controlled lab environment  
- Troubleshoot service issues and resource limitations  

---

## 🖥️ Lab Setup

### Host Environment
- **Main Host:** Windows laptop  
- **Virtualization Software:** VirtualBox  
- **Allocated Resources:** Multiple VMs for different roles  

### Virtual Machines (VMs)

| VM Name | OS | Role |
|---------|----|------|
| Wazuh Server VM | Ubuntu 24.04 | Wazuh Manager, Indexer, Dashboard |
| Ubuntu Agent VM | Ubuntu 24.04 | Monitored host, Wazuh agent installed |
| Windows Agent VM | Windows Server | Monitored host, Wazuh agent installed |
| Linux Attack VM | Linux (Kali/other) | Simulated attacks for testing alerts |

---

## ⚙️ Key Achievements

- Installed and configured **Wazuh Manager** to monitor multiple agents  
- Installed **Wazuh agents** on Ubuntu and Windows systems  
- Practiced **log collection, event monitoring, and alert management**  
- Troubleshot service failures (timeouts, indexer errors, agent communication)  
- Managed **VM resources** effectively under limited host memory  
- Documented **commands, configuration, and troubleshooting steps**  

---

## 🛠️ Wazuh Installation & Commands

### Installing Wazuh Manager (Ubuntu Server VM)

# Add Wazuh GPG key
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg

# Add Wazuh repository
echo "deb [signed-by=/usr/share/keyrings/wazuh-archive-keyring.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list

# Update packages
sudo apt update

# Install Wazuh Manager, Indexer, Dashboard
sudo apt install wazuh-manager wazuh-indexer wazuh-dashboard -y

# Enable and start Indexer
sudo systemctl enable wazuh-indexer
sudo systemctl start wazuh-indexer
sudo systemctl status wazuh-indexer
Installing Wazuh Agent (Ubuntu VM)

sudo apt update
sudo apt install wazuh-agent -y

# Register agent with Wazuh Manager
sudo /var/ossec/bin/agent-auth -m <MANAGER_IP>
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
sudo systemctl status wazuh-agent
Installing Wazuh Agent (Windows VM)
Download the Wazuh agent installer from Wazuh downloads⁠�
Run the installer and configure the Manager IP during setup
Start the Wazuh agent service via Services or PowerShell:
PowerShell

Start-Service WazuhSvc
⚠️ Troubleshooting & Lessons Learned
Service timeouts: Some Wazuh services failed to start due to limited VM memory
Indexer errors: Needed to adjust resources and remove stale lock files
Disk and RAM limitations: Learned to monitor and allocate proper resources in VirtualBox
Permissions issues: Required sudo privileges and careful command execution
Logs & alerts: Practiced reading Wazuh logs and understanding alerts from multiple hosts
📂 Folder Structure & Placeholders
screenshots/ – Dashboard, alerts, and agent status screenshots
dashboard.png – placeholder
ubuntu_agent.png – placeholder
windows_agent.png – placeholder
configs/ – Wazuh manager and agent configuration files
wazuh-manager.conf – placeholder
agent.conf – placeholder
docs/ – Lab notes, troubleshooting steps, lessons learned
lab_notes.md – placeholder
troubleshooting.md – placeholder
📸 Screenshots
Dashboard
�
Ubuntu Agent Logs
�
Windows Agent Logs
�
📂 Configuration Files
Wazuh Manager Config
Agent Config
📖 Lab Notes & Troubleshooting
Lab Notes
# Lab Notes
This file contains step-by-step notes from the SOC lab setup.
- Wazuh Manager installation on Ubuntu Server VM
- Agent installation and registration (Ubuntu & Windows)
- Troubleshooting common issues: timeouts, indexer failures, memory allocation
- Resource management in VirtualBox (CPU, RAM)
- Monitoring alerts and event logs
- Lessons learned and observations
🏆 Skills Gained
SOC architecture and monitoring workflow
Linux and Windows administration
Wazuh deployment, configuration, and troubleshooting
Virtual machine management (VirtualBox)
Security monitoring, event analysis, and incident response




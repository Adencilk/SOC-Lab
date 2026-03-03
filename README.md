# 🛡️ Security Operations Center (SOC) Lab Project

## Overview

This project demonstrates hands-on experience building a **SOC lab** using Wazuh for monitoring and analyzing cybersecurity events across multiple operating systems.

**Objectives:**
- Deploy and configure a SOC environment
- Monitor multiple hosts (Linux & Windows)
- Practice incident detection and response
- Troubleshoot real-world SOC deployment issues
- Document all processes for reproducibility

---

## Lab Setup

**Host Environment:** Windows laptop with VirtualBox  
**VMs:**

| VM Name          | OS          | Role / Purpose                       |
|-----------------|------------|-------------------------------------|
| Wazuh Server VM  | Ubuntu 24.04 | Wazuh Manager, Indexer, Dashboard   |
| Ubuntu Agent VM  | Ubuntu 24.04 | Monitored host, Wazuh agent installed |
| Windows Agent VM | Windows Server | Monitored host, Wazuh agent installed |
| Linux Attack VM  | Linux (Kali/Other) | Simulated attacks for testing alerts |

---

## Work Completed

1. Installed Ubuntu and Windows VMs for SOC lab
2. Installed Wazuh Manager, Indexer, and Dashboard
3. Installed and registered Wazuh agents on Ubuntu & Windows
4. Monitored logs and alerts from multiple hosts
5. Simulated attacks using Linux Attack VM
6. Troubleshot service timeouts, indexer errors, and permissions issues
7. Managed VM resources (RAM, CPU) for stability
8. Documented all commands, configurations, and observations
9. Practiced incident response and event analysis
10. Verified alert generation and log collection

---

## Commands & Installation

### Wazuh Manager (Ubuntu Server VM)
```bash
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/wazuh-archive-keyring.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list
sudo apt update
sudo apt install wazuh-manager wazuh-indexer wazuh-dashboard -y
sudo systemctl enable wazuh-indexer
sudo systemctl start wazuh-indexer
sudo systemctl status wazuh-indexer

## Skills Gained

- SOC deployment and management
- Wazuh Manager, Indexer, and Dashboard installation
- Wazuh agent configuration and multi-OS monitoring
- Linux system administration (Ubuntu 24.04)
- Windows system administration (Windows Server)
- Log collection, alert analysis, and event correlation
- Incident response simulations
- Troubleshooting deployment issues and memory limitations
- VirtualBox VM management (RAM, CPU, networking)
- Documentation of configurations, commands, and lab steps
- Resource allocation and performance optimization
- Reading and interpreting system logs and Wazuh alerts
- Hands-on multi-VM cybersecurity lab experience






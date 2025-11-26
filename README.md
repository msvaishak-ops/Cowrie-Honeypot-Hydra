# Cowrie-Honeypot-Hydra
SSH honeypot and brute force simulation using Hydra in an isolated network 
# 🛡️ Cowrie Honeypot Deployment and Brute-Force Attack Simulation using Hydra

## 📌 Abstract
This project demonstrates the deployment of a **Cowrie SSH honeypot** on Ubuntu and a **simulated brute-force attack** using **Hydra** from a Kali Linux attacker machine.  
The experiment is performed in an **isolated internal network in VirtualBox**, ensuring a safe environment.  
The honeypot logs attacker activity, including login attempts, passwords used, and SSH session metadata.
## 🏗️ Lab Architecture Diagram
┌────────────────┐ Internal Network (honeynet) ┌───────────────┐
│ Kali Linux │ Attack via SSH Brute Force (Hydra) ---> │ Ubuntu │
│ (Attacker) │------------------------------------------>│ Cowrie Honeypot│
│ IP: 192.168.56.20 │ IP: 192.168.56.10 │
└────────────────┘ └───────────────┘
## 🛠️ Tools Used
| Tool | Purpose |
|------|---------|
| **Cowrie Honeypot** | SSH/Telnet honeypot to capture attacks |
| **Hydra** | Brute-force tool for simulating password attacks |
| **Ubuntu (Victim VM)** | Runs Cowrie honeypot |
| **Kali Linux (Attacker VM)** | Executes brute-force |
| **VirtualBox Internal Network** | Safe isolated communication |
| **Netplan** | Linux network configuration |
## 🌐 Internal Network Configuration

| VM | Role | IP | Mode |
|----|------|----|------|
| **Ubuntu** | Cowrie Honeypot | `192.168.56.10` | Internal Network |
| **Kali Linux** | Attacker | `192.168.56.20` | Internal Network |

### 🖥️ **Ubuntu Netplan Configuration**
```yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s3:
      dhcp4: no
      addresses:
        - 192.168.56.10/24

![My screenshot](https://github.com/msvaishak-ops/Cowrie-Honeypot-Hydra/blob/main/ssh%20netsh%20command.png?raw=true)

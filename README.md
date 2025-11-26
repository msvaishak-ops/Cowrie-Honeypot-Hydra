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


<img width="1280" height="800" alt="cowrie log of hydra attack" src="https://github.com/user-attachments/assets/165575a6-15f1-4ad5-9a9c-772dc1a9e26f" /><img width="1600" height="900" alt="ip setup and ping ubuntu" src="https://github.com/user-attachments/assets/6e01e6ba-704b-428f-9473-4b330b40c77d" />

<img width="1600" height="900" alt="hydra command execution" src="https://github.com/user-attachments/assets/7a61a529-0255-43be-a5a5-d745c1225e1e" />
<img width="1280" height="800" alt="pinging kali" src="https://github.com/user-attachments/assets/7d5ab3c8-52e7-419f-a9d1-0aa420bdc94c" />

<img width="1280" height="800" alt="cowrie start and status" src="https://github.com/user<img width="1280" height="800" alt="net config and pinging" src="https://github.com/user-attachments/assets/197b0705-78ec-4e33-9207-f61b937e4ade" />
-attachments/assets/c2e3af17-30e6-44a1-b551-0f8db0c637ac" />

<img width="1280" hei<img width="1280" height="800" alt="cowrie logs" src="https://github.com/user-attachments/assets/679da717-e0a2-4a0a-955b-359652284153" />
ght="800" alt="cowrie json" src="https://github.com/user-attachments/assets/0612acfe-47ac-4d1c-b36e-899a2696ac49" />

![image alt]https://github.com/msvaishak-ops/Cowrie-Honeypot-Hydra/blob/main/cowrie%20log%20of%20hydra%20attack.png?raw=true




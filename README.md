# Cybersecurity-Lab-Setup
This project sets up a cybersecurity lab with Kali Linux, Ubuntu, and Windows for penetration testing and security research.

What this project does.
Steps to replicate the setup.
Tools used (VirtualBox, Kali, Ubuntu, Nmap, UFW).
Key takeaways.


# Cybersecurity Lab Setup

This project sets up a **penetration testing lab** using VirtualBox with **Kali Linux (attacker), Ubuntu (target), and Windows (optional)**.

## 📌 Steps:
1. **Create Virtual Machines**
2. **Configure Network (NAT & NAT Network)**
3. **Test Connectivity (Ping & Nmap)**
4. **Enable SSH & Firewall (UFW)**
5. **Persist Network Configurations**

## 🔧 Tools Used:
- **Oracle VirtualBox** (VM management)
- **Kali Linux** (Attacker system)
- **Ubuntu** (Target system)
- **Nmap** (Network scanner)
- **UFW** (Firewall management)
- **SSH** (Secure remote access)

## 🚀 Learning Outcomes:
- Virtualization and networking basics.
- Firewall configuration & SSH hardening.
- Penetration testing lab setup.

## Lets dive into step by step process

🔹 Step 1: Setting Up Virtual Machines
✅ What I did:

Installed Oracle VirtualBox to create and manage VMs.
Downloaded ISO files for:
Ubuntu (Target system)
Kali Linux (Attacker system)
Windows 10 (Optional)
Created three virtual machines (VMs) for each OS.

🧠 What I learned:

How to create VMs in VirtualBox.
The importance of a controlled testing environment in cybersecurity.



🔹 Step 2: Configuring Network Settings
✅ What I did:

Configured two network adapters for each VM:
NAT (For Internet Access)
NAT Network (For Internal VM Communication)
Set up static IPs for better connectivity:
Kali: 10.0.2.100
Ubuntu: 10.0.2.200

🧠 What I learned:

Difference between NAT and NAT Network:
NAT → Provides internet access to VMs.
NAT Network → Allows VMs to communicate with each other.
How to assign static IP addresses to interfaces.



🔹 Step 3: Testing Connectivity
✅ What I did:

Verified the network interfaces (ip a).
Used ping to test connectivity between VMs.
Ran Nmap from Kali to scan Ubuntu (nmap -A 10.0.2.200).
Enabled SSH server on Ubuntu (sudo apt install openssh-server).
Connected to Ubuntu via SSH from Kali (ssh vboxuser@10.0.2.200).

🧠 What I learned:

How to use ping to test network connectivity.
How to scan systems for open ports using Nmap.
How to configure and use SSH for remote access.



🔹 Step 4: Firewall & Security Settings
✅ What I did:

Installed and configured UFW (Uncomplicated Firewall) on Ubuntu.

Allowed SSH traffic:
Open Terminal - sudo ufw allow 22/tcp

Enabled the firewall: 
open Terminal - sudo ufw enable

Verified firewall rules:
Open Terminal - sudo ufw status verbose
🧠 What I learned:

How firewalls restrict network traffic.
How to allow/block specific ports and protocols.
Why securing SSH is critical in cybersecurity labs.



🔹 Step 5: Persisting Configuration (Networking)
✅ What I did:

Edited network configuration files:
Ubuntu: /etc/netplan/00-installer-config.yaml
Kali Linux: /etc/network/interfaces
Applied settings with:

open Terminal -
sudo netplan apply  # Ubuntu
sudo systemctl restart networking  # Kali

🧠 What I learned:

How Linux persists network configurations across reboots.
How to troubleshoot connectivity issues with Netplan and interfaces files.



🎯 What Can I Learn from Project 1?
🔍 Key Cybersecurity Concepts:
Virtualization: Running multiple OSes in an isolated environment.
Network Security: Configuring firewall rules, IP settings, and SSH security.
Penetration Testing Basics: Using Nmap for reconnaissance.
System Administration: Managing users, services, and network configs.

💡 Real-World Applications:
This setup mimics a corporate network, allowing security teams to practice penetration testing.
Used in SOC (Security Operations Centers) for threat detection labs.
Helps red teams (attackers) and blue teams (defenders) test security tools.


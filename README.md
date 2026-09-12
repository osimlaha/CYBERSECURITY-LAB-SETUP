<div align="center">

# 🔐 Cybersecurity Lab Environment Setup[cite: 1]

**Building an isolated virtual lab for penetration testing and ethical hacking practice**[cite: 1]

<br />

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" alt="Cybersecurity" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" alt="VirtualBox" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" alt="Network" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Pentesting" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Ethical Hacking" />
</p>

</div>

---

## 📌 Project Overview
This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux[cite: 1]. The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly[cite: 1]. The lab is configured on a private virtual network so that additional target machines can be added later for authorized security testing[cite: 1].

---

## 🎯 Objectives
* Install and configure VirtualBox[cite: 1].
* Install and import Kali Linux as a virtual machine[cite: 1].
* Create a private **NAT Network** for the cybersecurity lab[cite: 1].
* Configure network connectivity for Kali Linux[cite: 1].
* Assign a consistent IP address to the Kali VM[cite: 1].
* Verify network connectivity and DNS resolution[cite: 1].
* Take a clean VM snapshot for recovery[cite: 1].
* Document the complete setup process[cite: 1].
* Prepare the environment for future cybersecurity projects[cite: 1].

---

## 🛡️ Purpose of the Lab
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing[cite: 1]. It supports activities such as:
* Network reconnaissance[cite: 1]
* Port scanning[cite: 1]
* Vulnerability assessment[cite: 1]
* Packet analysis[cite: 1]
* Web security testing[cite: 1]
* Exploitation practice[cite: 1]
* Security-tool experimentation[cite: 1]

> ⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test[cite: 1]. Do not use the lab or its tools to attack unauthorized systems[cite: 1].

---

## 🏗️ Lab Architecture
![Lab Architecture Diagram](1-screenshot-title-image.png)[cite: 1]

Additional target machines can be added to the same virtual network in future projects[cite: 1].

---

## ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration |
| :--- | :--- |
| **Host OS** | Windows 10[cite: 1] |
| **Host RAM** | 8 GB[cite: 1] |
| **Processor** | Intel Core i7[cite: 1] |
| **Hypervisor** | VirtualBox 7.2[cite: 1] |
| **Security OS** | Kali Linux 2026.2[cite: 1] |
| **Kali RAM** | 2048 MB[cite: 1] |
| **Virtual Network** | NAT Network[cite: 1] |
| **Network Address** | 10.0.0.0/24[cite: 1] |
| **Kali IP Address** | 10.0.0.2/24[cite: 1] |
| **Default Gateway** | 10.0.0.1[cite: 1] |
| **DNS Server** | 8.8.8.8[cite: 1] |
| **Future VM Range** | 10.0.0.3–10.0.0.99[cite: 1] |

---

## 🪜 Lab Setup Procedure

### Step 1. Install 7-Zip
7-Zip was installed to extract the Kali Linux virtual-machine package, which is commonly distributed as a `.7z` archive[cite: 1].

### Step 2. Install VirtualBox
VirtualBox was installed to serve as the hypervisor for the lab environment[cite: 1].

### Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox with the following configuration[cite: 1]:
* **Network Name:** NatNetwork[cite: 1]
* **IPv4 Prefix:** 10.0.0.0/24[cite: 1]
* **DHCP:** Enabled[cite: 1]
* **IPv6:** Disabled[cite: 1]

![NAT Network Settings](2-screenshot-network-settings-1.png)[cite: 1]

A **NAT Network** allows multiple virtual machines connected to it to communicate with one another while also maintaining outbound network connectivity[cite: 1]. 

### Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official website and imported into VirtualBox[cite: 1]. The VM was allocated **2048 MB of RAM**[cite: 1]. The network adapter was configured as follows:
* **Attached to:** NAT Network[cite: 1]
* **Network:** NatNetwork[cite: 1]
* **Adapter Type:** Intel PRO/1000 MT Desktop[cite: 1]

![Kali Linux Import](3-screenshot-kali-linux.png)[cite: 1]
A shared folder was also configured for transferring files between the host OS and the Kali VM[cite: 1].

### Step 5. Configure the Kali Linux Network
The Kali Linux network was configured with a consistent IPv4 address[cite: 1]:
* **IP Address:** 10.0.0.2[cite: 1]
* **Subnet Mask:** 255.255.255.0[cite: 1]
* **Gateway:** 10.0.0.1[cite: 1]
* **DNS:** 8.8.8.8[cite: 1]

A consistent IP address streamlines lab documentation and future exercises[cite: 1].
![Kali Network Settings](4-screenshot-kali-network-settings.png)[cite: 1]

### Step 6. Create a Clean VM Snapshot
A VirtualBox snapshot named `Clean Kali - Network Setup` was created to represent the clean baseline of the laboratory[cite: 1]. This ensures the machine can be restored if future exercises damage the configuration[cite: 1].

---

## 🔎 Lab Verification

| ✅ Test | 🧾 Command | 🎯 Expected Result |
| :--- | :--- | :--- |
| **Check IP address** | `ip a` | Correct Kali IP displayed[cite: 1] |
| **Test gateway** | `ping 10.0.0.1` | Successful replies[cite: 1] |
| **Test Internet connectivity** | `ping 8.8.8.8` | Successful replies[cite: 1] |
| **Test DNS resolution** | `nslookup networkwalks.com` | Domain resolves[cite: 1] |
| **Verify Nmap** | `nmap --version` | Nmap version displayed[cite: 1] |
| **Verify snapshot** | Restore snapshot and run `ip a` | Baseline configuration restored[cite: 1] |

---

## 🐞 Problems Encountered & Solutions

### Problem 1: Internet Connectivity After Static IP Configuration
After manually configuring IPv4 settings, Internet connectivity occasionally failed[cite: 1]. 
**Solution:** The issue was resolved by modifying the network manager timeout using `sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0`, followed by a network restart[cite: 1]. *(Note: Network interface names may differ between systems[cite: 1].)*

### Problem 2: VirtualBox VT-x / Virtualization Error
The VM initially failed to start because hardware virtualization was disabled in the system BIOS/UEFI[cite: 1].
**Solution:** The computer was restarted into the BIOS settings, Intel VT-x (hardware virtualization) was enabled, the configuration was saved, and the Kali VM successfully booted upon restart[cite: 1].

---

## 💡 What I Learned

* **NAT vs NAT Network:** A NAT Network allows multiple connected VMs to communicate with each other while providing external internet access, making it ideal for a multi-machine lab[cite: 1].
* **Virtual Machine Networking:** Gained experience in connecting virtual network adapters to different network types and understanding how they affect inter-machine communication[cite: 1].
* **Static IP Configuration:** Learned to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Linux[cite: 1].
* **VM Snapshots:** Discovered the importance of creating clean snapshots before risky activities to guarantee a known-good recovery point[cite: 1].
* **Documentation:** Realized that tracking commands, configurations, screenshots, problems, and solutions is essential for professional cybersecurity projects[cite: 1].

---

## 🔐 Security & Ethical Use
This laboratory is intended strictly for education purposes only[cite: 1].

---

## 🔗 Tools & Resources
* **7-Zip:** [Download Here](https://7-zip.org/download.html)[cite: 1]
* **VirtualBox:** [Download Here](https://virtualbox.org/wiki/Downloads)[cite: 1]
* **Kali Linux:** [Download Here](https://kali.org/get-kali)[cite: 1]

---

## 👤 Author
**[Your Name Here]**  
*Cybersecurity Professional*[cite: 1]  
LinkedIn: [Your LinkedIn Profile][cite: 1]

> **Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub[cite: 1]

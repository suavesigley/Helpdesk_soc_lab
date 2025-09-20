# 🧰 VirtualBox Configuration Guide

This document outlines the VirtualBox setup used to host the Help Desk + SOC Analyst lab. It includes host specs, VM configurations, and networking details to simulate real-world IT support and security workflows.

---

## 🖥️ Host System Specs

| Component       | Value              |
|----------------|--------------------|
| OS             | Windows 10/11      |
| CPU            | Quad-core (Intel/AMD) |
| RAM            | 16GB               |
| Storage        | 500GB+ SSD         |
| Virtualization | Enabled in BIOS    |
| Hypervisor     | VirtualBox (latest) |

---

## 📦 VirtualBox Global Settings

- **Default Machine Folder**: `C:\VMs`
- **Clipboard Sharing**: Bidirectional
- **Drag and Drop**: Enabled (Host ↔ Guest)
- **Shared Folders**: Optional for screenshots/logs
- **Snapshots**: Used before major changes

---

## 🧱 VM Configuration Summary

| VM Name         | OS               | RAM  | NIC Type         | Purpose               |
|----------------|------------------|------|------------------|------------------------|
| `pfSense`       | FreeBSD-based    | 512MB| 2 NICs (LAN/WAN) | Firewall & segmentation|
| `Kali Linux`    | Kali Rolling     | 2GB  | Host-only        | Attacker machine       |
| `Metasploitable`| Ubuntu 14.04     | 1GB  | Host-only        | Vulnerable target      |
| `Ubuntu Desktop`| Ubuntu 22.04     | 2GB  | Host-only        | Simulated user PC      |
| `WinServer-AD`  | Windows Server 2019 | 4GB  | Host-only        | Active Directory + Shares|

---

## 🔌 Networking Setup

### pfSense NICs
- **WAN Adapter**: NAT (Internet access)
- **LAN Adapter**: Host-only (internal lab)

### Other VMs
- Connect to **pfSense LAN** via Host-only adapter
- All traffic routed through pfSense for segmentation and logging

---

## 🧪 Tips for Stability & Performance

- Use **Snapshots** before testing exploits or major config changes
- Enable **VT-x/AMD-V** in VM settings for better performance
- Allocate **CPU cores** based on workload (e.g., Kali = 2 cores)
- Use **VirtualBox Guest Additions** for clipboard and resolution support

---

## 📁 Next Steps

Continue to:
- [pfSense Setup Guide](../setup/pfSense-setup.md)
- [VM Build Notes](../setup/vm-build-notes.md)

---

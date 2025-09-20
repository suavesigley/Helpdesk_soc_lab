# 🔐 pfSense Setup Guide

This guide documents the installation and configuration of pfSense as a virtual firewall within the Help Desk + SOC Analyst lab. pfSense is used to segment the lab network, simulate real-world firewall rules, and log traffic for security analysis.

---

## 📦 VM Configuration (VirtualBox)

| Setting        | Value              |
|----------------|--------------------|
| OS Type        | Other/FreeBSD      |
| RAM            | 512MB              |
| CPU            | 1 core             |
| NIC 1 (WAN)    | NAT Adapter        |
| NIC 2 (LAN)    | Host-only Adapter  |
| Storage        | 4GB (dynamic)      |
| ISO Used       | `pfSense-CE-2.7.2-RELEASE.iso` |

---

## 🧱 Installation Steps

1. Download pfSense ISO from [pfsense.org/download](https://www.pfsense.org/download/)
2. Create a new VM in VirtualBox with the settings above
3. Attach the ISO and boot the VM
4. Follow the installer prompts:
   - Accept default keymap
   - Use guided disk setup
   - Reboot after install
5. On reboot, pfSense will assign interfaces:
   - `em0` → WAN (NAT)
   - `em1` → LAN (Host-only)

---

## 🌐 LAN Configuration

1. Access pfSense via browser: `http://192.168.1.1`
2. Default credentials:
   - Username: `admin`
   - Password: `pfsense`
3. Run the setup wizard:
   - Set hostname: `pfsense.local`
   - Set DNS: `1.1.1.1`, `8.8.8.8`
   - Set LAN IP: `192.168.10.1/24`
   - Set admin password

---

## 🔒 Firewall Rules

### LAN → Allow All (Initial Setup)
- Interface: LAN
- Protocol: Any
- Source: LAN net
- Destination: Any
- Action: Allow

### WAN → Block All (Default)
- pfSense blocks unsolicited inbound traffic by default

---

## 🧪 Logging & Monitoring

- Enable logging for all firewall rules
- Use **Status → System Logs → Firewall** to monitor traffic
- Optional: Install **pfBlockerNG** for DNS filtering

---

## 🧩 Integration with Lab

- All VMs (Kali, Ubuntu, Metasploitable, Windows Server) connect to LAN via Host-only adapter
- pfSense routes traffic and enforces segmentation
- Use NAT for internet access (e.g., Kali updates)

---

## 📁 Next Steps

Continue to:
- [VM Build Notes](../setup/vm-build-notes.md)
- [Simulations](../simulations/onboarding-ticket.md)

---

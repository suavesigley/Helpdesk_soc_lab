# 🛠️ Help Desk + SOC Analyst Lab

A hands-on homelab designed to simulate real-world IT support and security operations workflows. Built using VirtualBox, pfSense, and multiple virtual machines to emulate user environments, attack surfaces, and network segmentation.

## 🔍 Lab Purpose

This lab demonstrates:
- Tier 1 Help Desk workflows (onboarding, troubleshooting, password resets)
- SOC Analyst simulations (phishing alerts, access investigations, MITRE-aligned playbooks)
- Network segmentation and firewall control via pfSense
- Attack and defense scenarios using Kali Linux and Metasploitable

## 🧱 Lab Topology

![Topology Diagram](topology-diagram.png)

- `pfSense`: Virtual firewall for network segmentation
- `Ubuntu`: Simulated user workstation
- `Kali Linux`: Attacker machine for Red Team scenarios
- `Metasploitable`: Vulnerable target for exploitation
- `Windows Server (optional)`: Active Directory domain controller for access control simulations

## 📁 Repo Structure

```plaintext
helpdesk-soc-lab/
├── setup/                  # Environment build guides
├── simulations/            # Real-world ticket scenarios
├── troubleshooting/        # Technical issue resolutions
├── playbooks/              # Help Desk + SOC workflows

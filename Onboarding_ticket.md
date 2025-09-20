# 🧑‍💼 Help Desk Simulation: New Hire Onboarding

## 🎯 Ticket Summary

> A new employee, Jordan Smith, has joined the company. You're tasked with creating their Active Directory account, assigning them to the correct groups, and ensuring they can access the Finance shared folder.

---

## 🧱 Environment

- **Domain Controller**: `WinServer-AD` (Windows Server 2019)
- **Domain**: `corp.local`
- **User Workstation**: `Ubuntu Desktop`
- **Shared Folder**: `\\WinServer-AD\Finance`

---

## 🛠️ Tasks Performed

### ✅ Account Creation
- Created user: `jsmith@corp.local`
- Set password: `TempPass123!` (user prompted to change on first login)
- Enabled account and set expiration policy

### ✅ Group Assignment
- Added to:
  - `Finance`
  - `Domain Users`

### ✅ Shared Folder Setup
- Created folder: `C:\Shares\Finance`
- Set NTFS permissions:
  - `Finance` group → Read/Write
- Enabled sharing:
  - Share name: `Finance`
  - Permissions: `Finance` group → Full Control

### ✅ Drive Mapping (Optional)
- Created

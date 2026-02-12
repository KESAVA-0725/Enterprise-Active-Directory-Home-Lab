
# 🏢 Active Directory Home Lab – Complete Implementation

## 📌 Project Overview

This project demonstrates a complete Active Directory Home Lab implementation using Windows Server and Windows 10 in a virtualized environment.

The lab covers:

- Active Directory Domain Services (AD DS)

- DNS & DHCP Configuration

- RAS/NAT Configuration

- Bulk User Creation using PowerShell (1000+ Users)

- Group Policy Management (GPO)

- File Services & Network Sharing

- NTFS vs Share Permissions

- FSRM (Quota & File Screening)

- Access-Based Enumeration (ABE)

- Service Accounts & Single-Purpose Computer Setup

## 🖥️ Lab Architecture
### 🔹 Virtual Environment

- VirtualBox / VMware Workstation

1 × Domain Controller (Windows Server 2019/2022)

1 × Client Machine (Windows 10/11)

### 🔹 Network Design
Component	Configuration
- DC Internal IP	172.16.0.1
- Subnet Mask	255.255.255.0
- DHCP Scope	172.16.0.100 – 172.16.0.200
- DNS	127.0.0.1
- Domain Name	itsmine.com

Two NICs were configured on the Domain Controller:

- INTERNET (DHCP from router)

- INTERNAL (Static 172.16.0.1)

## 🏗️ 1. Active Directory Setup

- Installed Active Directory Domain Services (AD DS)

- Promoted server to Domain Controller

- Created new forest: itsmine.com

- Verified DNS & domain functionality

- Joined Windows 10 client to domain

- Domain authentication was successfully tested from client machine.

## 👥 2. Bulk User Creation (PowerShell Automation)

- Created names.txt containing multiple usernames

- Developed PowerShell script using New-ADUser

- Configured Execution Policy

- Automatically created 1000+ domain users

This demonstrates automation and administrative efficiency in AD environments.

## 🛡️ 3. Group Policy Implementation (GPO)
### 🔐 Password Policy

- Minimum password length: 7 characters

- Password complexity enabled

- Enforced domain-wide

Tested with weak password rejection

### 🔒 Account Lockout Policy

- Configured lockout threshold

- Set lockout duration

- Prevented brute-force login attempts

### 🚫 Restriction Policies

- Disabled Control Panel access

- Blocked USB storage devices

- Enforced desktop wallpaper policy

### 🗂️ Drive Mapping Policy

- Automatically mapped shared folder to users

- Applied via GPO at OU level

- Verified on client machine

## 📂 4. File Services & Network Sharing
### 🔹 Shared Folder Configuration

- Created SHARED folder

- Configured Share permissions

- Configured NTFS permissions

### 🔹 Network Drive Mapping

- Manual mapping via \AD-DC\SHARED

- Automatic mapping using GPO

## ⚖️ 5. NTFS vs Share Permissions Scenarios

Implemented real-world access control scenarios:

### 📁 Marketing Folder

- Marketing Intern → Read-only access

- No modification rights

### 📁 HR Folder

- HR Staff → Full control

- Others → No access

### 📁 Vendor Folder

- Vendor group → Upload-only access

- Restricted file exposure

### 📁 IT Software Repository

- IT staff → Access to Software

- Senior IT → Exclusive access to Licenses subfolder

## 📊 6. File Server Resource Manager (FSRM)
### 📏 Quota Management

- Applied storage limit to SHARED folder

- Prevented excessive disk usage

### 🚫 File Screening

- Blocked audio & video file types

- Applied custom file screen templates

- Verified restriction functionality

## 👁️ 7. Access-Based Enumeration (ABE)

- Enabled ABE on shared folders

- Users can only see folders they have permission to access

Verified with:

- Senior_IT user

- Senior_HR user

- Restricted folders remain hidden

This improves security and reduces unnecessary visibility.

## 🖥️ 8. Service Account & Single-Purpose System
### 🔹 Service Account Creation

- Created dedicated AD service account

- Disabled password expiration

### 🔹 Auto Logon Configuration

- Used Autologon tool

- Configured automatic login

### 🔹 Browser Auto Startup

- Configured Chrome to open specific webpage

- Added shortcut to Startup folder

- Disabled sleep mode

This simulates a kiosk / display system scenario.

### 🧠 Skills Demonstrated

- Active Directory Administration

- Windows Server Management

- PowerShell Automation

- Group Policy Management

- Network Configuration (DHCP, DNS, NAT)

- File Server Management

- NTFS Permission Handling

- Role-Based Access Control (RBAC)

- Access-Based Enumeration

- Security Policy Implementation

### 🎯 Learning Outcomes

- Built a fully functional enterprise-like AD environment

- Implemented real-world access control scenarios

- Automated large-scale user provisioning

- Strengthened domain security using policies

- Practiced file server management and permission design

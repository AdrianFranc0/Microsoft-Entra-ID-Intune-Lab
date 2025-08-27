#  Microsoft Entra ID + Intune Lab  

This lab simulates modern IT administration using **Microsoft Entra ID** for identity & access management and **Microsoft Intune** for endpoint/device management.  
It demonstrates skills in **user management, MFA enforcement, device enrollment, compliance, configuration, application deployment, and endpoint hardening.  

---
In this lab, I built a simulated enterprise environment leveraging Microsoft Entra ID (Azure AD) and Microsoft Intune to demonstrate modern identity and device management.

Identity Management (Entra ID)

Configured cloud-based directory services for centralized authentication and access control.

Set up Multi-Factor Authentication (MFA) and explored Conditional Access policies to simulate Zero Trust.

Device Enrollment & Management (Intune)

Enrolled Windows endpoints into Intune for centralized management.

Applied baseline security configurations and compliance policies.

App Management

Deployed Microsoft 365 applications (Teams, Outlook, OneDrive) through Intune.

Configured Company Portal for self-service app installs.

Policy Enforcement

Created compliance rules (e.g., password requirements, AV enabled, BitLocker).

Applied device configuration profiles to enforce enterprise standards.

---

## Step 1 – Entra ID Setup  

**Description**:  
Created a new **Microsoft Entra ID tenant** to simulate a company directory. Added three users:  
- Backup Admin (break-glass account).  
- IT Technician test account.  
- Regular Admin account.  

Organized users into groups (*Lab Users* and *Intune Users*) for targeted policy assignments.  

<p align="center">  
<img src="https://i.imgur.com/86rO4Kq.png" width="900" style="height:900;">  
</p>  

---

## Step 2 – MFA Conditional Access Policy  

**Description**:  
Created a Conditional Access policy requiring **Multi-Factor Authentication (MFA)** for the Lab Users group.  
Tested by logging in with the IT Tech user and confirming MFA prompts.  

<p align="center">  
<img src="https://i.imgur.com/yImy0QL.png" width="600" style="height:auto;">  
</p>  

<p align="center">  
<img src="https://i.imgur.com/v96S8EQ.png" width="600" style="height:auto;">  
</p>  

---

## Step 3 – Device Enrollment in Intune  

**Description**:  
Deployed a Windows 10 Pro VM and joined it to **Entra ID**. Synced the device into Intune, where it now shows up under managed devices.  

<p align="center">  
<img src="https://i.imgur.com/4GCGbMx.png" width="600" style="height:auto;">  
</p>  

<p align="center">  
<img src="https://i.imgur.com/kYEVohb.png" width="600" style="height:auto;">  
</p>  
---

## Step 4 – Compliance Policy  

**Description**:  
Created a **Windows 10 Compliance – Baseline Security** policy to simulate enterprise requirements:  
- 12-character minimum passwords  
- BitLocker encryption  
- Secure Boot enabled  
- Defender AV & real-time protection  

Note: In VM testing, compliance showed `0 devices` due to virtual limitations, but this demonstrates how compliance dashboards track device posture in production.  

<p align="center">  
<img src="https://i.imgur.com/TTvZUaE.png" width="600" style="height:auto;">  
</p>  

---

## Step 5 – Configuration Profile (Security Hardening)  

**Description**:  
Created a **Windows 10 Security Hardening – Baseline** profile to enforce:  
- Screen lock after 10 minutes  
- Automatic Windows Updates  
- USB device restrictions  

Assigned to the Intune group. On sync, devices show “managed by organization.”  

<p align="center">  
<img src="https://i.imgur.com/iqsDCvI.png" width="600" style="height:auto;">  
</p>  

---

## Step 6 – Application Deployment  

**Description**:  
Simulated enterprise app deployment by pushing **7-Zip** via Intune.  
This same process works for Chrome, Office, or other business-critical software.  

<p align="center">  
<img src="https://i.imgur.com/pacoOZa.png" width="600" style="height:auto;">  
</p>  

---

## Step 7 – Endpoint Security (Defender AV & Firewall)  

**Description**:  
Created two endpoint security policies:  

- **Defender Antivirus Policy**: enabled behavior monitoring, cloud-delivered protection, real-time monitoring, and scanning of downloads/attachments.  
- **Firewall Policy**: enforced Defender Firewall ON for Domain, Private, and Public profiles.  

<p align="center">  
<img src="https://i.imgur.com/cuR2tvJ.png" width="600" style="height:auto;">  
</p>  

<p align="center">  
<img src="https://i.imgur.com/PVoqpfV.png" width="600" style="height:auto;">  
</p>  

---

## Step 8 – Device Sync (Wrap-Up)  

**Description**:  
Performed a **manual sync** from the enrolled VM after applying policies.  
Syncing is important because:  
- Ensures devices pull **latest policy changes** immediately (instead of waiting hours).  
- Allows IT admins to confirm changes reached the endpoint.  
- Critical for **troubleshooting** and validating security/app deployments.  

<p align="center">  
<img src="https://i.imgur.com/T5eftTR.png" width="600" style="height:auto;">  
</p>  

---

# ✅ Summary  
  

- Identity & Access: Managed users + enforced MFA  
- Device Management: Enrolled endpoints into Intune  
- Compliance: Baseline security requirements  
- Configuration: Locked down Windows settings  
- App Deployment: Centralized software distribution  
- Endpoint Security: Hardened with AV & firewall  
- Device Sync: Verified policy + app enforcement  

📌 Demonstrates the ability to manage **users, devices, and security in Microsoft 365 environments.  

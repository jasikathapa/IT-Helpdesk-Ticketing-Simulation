
# 🎫 Ticket: Domain Trust / Authentication Failure

## Ticket ID
HD-0002

## Category
Active Directory / Authentication Issue

## Priority
High

---

## User Reported Issue
Unable to log in to the domain after system changes were made on the Domain Controller.

---

## Issue Description

After renaming the Domain Controller, Active Directory authentication failed and domain logins were no longer possible. This resulted in a broken trust relationship between the server and the domain.\

---
<img width="600" height="600" alt="AD broken" src="https://github.com/user-attachments/assets/f2d7a3e7-8e67-489f-95e4-a28df3a1dcda" />


## Root Cause
- Domain Controller computer name was changed after Active Directory was configured
- This caused a disruption in domain authentication and secure channel communication

---

## Investigation Performed
- Verified domain login failures across client machines
- Checked Domain Controller availability and configuration
- Identified issue occurred immediately after system name change

---

## Resolution
Booted the system into **Safe Mode with Networking**  
- Accessed a local administrative recovery account  
- Restored system configuration to re-establish domain functionality  
- Reverted the Domain Controller name to its original configuration  
- Restarted the system and verified Active Directory services were operational  

---
<img width="700" height="600" alt="Screenshot 2026-05-20 231740" src="https://github.com/user-attachments/assets/9106fde8-7a8c-472c-bbd7-06aa7a1cca07" />


## Post-Incident Action
After service restoration, domain controller compuetr name  was changed using PowerShell for reference:

```powershell
Rename-Computer -NewName "NEW-DC-NAME" -Restart
```
---

## Outcome
Domain authentication was restored successfully and clients were able to rejoin and authenticate to the domain.

---

## Key Learning
Changing the identity of a Domain Controller can disrupt Active Directory trust relationships and should only be done following proper planning and best practices.

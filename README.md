# Foundations of Active Directory

## Project Overview
This lab introduced me to the fundamentals of **Active Directory (AD)** within a simulated Windows enterprise environment. Through hands-on exercises, I explored domain structures, authentication processes, user enumeration, and common security misconfigurations. The project mirrors real-world AD environments used in corporate networks and lays the groundwork for both blue team and red team perspectives.

---

## Why Active Directory Matters
Active Directory serves as the backbone of identity and access management in nearly all enterprise Windows networks. Mastering its functionality is critical for:
- Securing digital assets and managing permissions
- Detecting misconfigurations or privilege escalations
- Supporting user lifecycle operations within organizations
- Laying the foundation for red and blue team security operations

---

## Objectives
- Understand the structure of Active Directory and how domain components are organized  
- Perform enumeration of users, groups, and domain controllers  
- Explore AD authentication flows and permission hierarchies  
- Identify typical attack surfaces in AD environments

---

## Tools & Technologies
- **Platform**: Hack The Box Academy  
- **Tools Used**: Windows Command Line, PowerShell, ADAC, Group Policy Management Console  
- **Commands Used**: `whoami/priv`, `Get-ADGroup`, `Get-ADUser`, `New-ADUser`, `New-ADGroup`, `Add-ADGroupMember`, etc.  
- **Environment**: Simulated Windows Domain  
- **Skills Practiced**: AD Enumeration, Group & User Management, GPO Implementation

---

## Steps Taken

1. **Organizational Unit & Group Creation**
   - Used ADAC to create an `OU` named `Security Analysts`, and added a group `Security Analysts` to it  
   - Created and deleted users as part of lifecycle management

2. **Group Membership & GPO Assignment**
   - Added users to the `Security Analysts` group  
   - Created a Group Policy Object (`Security Analysts Control`) and linked it to the OU to enforce configuration rules

3. **PowerShell Replication**
   - Repeated all tasks from user, group, and OU creation to GPO linking using `ActiveDirectory` PowerShell module  
   - Demonstrated automation-ready workflow for enterprise use

---

## Key Skills & Learnings
- Built hands-on familiarity with AD layout, schema, and administrative interfaces  
- Practiced both GUI and CLI approaches to AD administration  
- Strengthened understanding of domain authentication, GPO behavior, and identity management  
- Gained insight into operational and security implications of AD environments


---

## All visuals stored in [`screenshots/`](screenshots/) subfolder

<details>
<summary><strong> Key Visuals</strong> (click to expand)</summary>

- **OU Creation**
  
![OU Creation](screenshots/create-ou-adac.png)
  
- **User Management**
  
![User Management](screenshots/add-user-adac.png)
  
- **Group Policy Applied**
  
![Group Policy Applied](screenshots/gpmc-password-policy-confirm.png)

</details>

---

## Files Included

- [Fundamentals Guided Lab](/Guided-Lab/AD-Fundamentals.md): Detailed documentation of tasks using ADAC and PowerShell  
- [AD Powershell Commands](/Guided-Lab/AD-Commands.md): PowerShell Command line reference used throughout the lab  

---

## Result
Completed the lab with a strong grasp of Active Directory structure, administration, and security posture. This project developed my skills in managing AD-supported environments, essential for roles in **IT support**, **SOC operations**, and **enterprise security**.

---

*[Visit My GitHub Landing Page](https://github.com/Jovaan-Whitton)*

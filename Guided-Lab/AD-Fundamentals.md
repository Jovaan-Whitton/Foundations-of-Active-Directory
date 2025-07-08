# 🏢 Foundations of Active Directory

## Project Overview
This lab introduced me to the fundamentals of **Active Directory (AD)** within a simulated Windows enterprise environment. Through hands-on exercises, I explored domain structures, authentication processes, user enumeration, and common security misconfigurations. The project mirrors real-world AD environments used in corporate networks and lays the groundwork for both blue team and red team perspectives.

---

## Lab Objectives
- Understand the structure of Active Directory and how domain components are organized
- Create Organizational Units (OUs)  
- Add and remove users  
- Create and manage groups  
- Assign users to groups  
- Apply Group Policy Objects (GPOs)

--- 

## Key Skills & Learning
- Developed working knowledge of AD layout and command-line interaction
- Practiced user and group enumeration to support identity auditing
- Gained foundational understanding of Windows domain authentication
- Identified risks that arise from excessive privileges or weak group policy

---

## 1. Add New Users
### ADAC Method
- Open **ADAC** 
- Navigate to the IT OU. inlanefreight.local → Corp → Employees → HQ-NYC → IT
- Right-click the IT OU → New → User
- Fill in user details for `Andromeda Cepheus`, `Orion Starchaser`, `Artemis Castillo`
- Attributes included are full name, email, display name and that the user must change password at next logon

### PowerShell Equivalent
New-ADUser -Name "Artemis Castillo" -AccountPassword (ConvertTo-SecureString -AsPlainText(Read-Host "enter a secure password") -Force) -enabled $true -other attributes @{'title' "Analyst" ; 'mail' = "a.castillo@inlanefreight.local}
-UserPrincipalName "jane.doe@labdomain.local" `
-Path "OU=Marketing,DC=labdomain,DC=local" `
-AccountPassword (ConvertTo-SecureString "P@ssw0rd123" -AsPlainText -Force) `
-Enabled $true

---

## 2. Delete a User
### ADAC Method
- Locate the user by right clicking on the find option of the employees OU.
- Right-click → Delete

### PowerShell Equivalent
- Remove-ADUser -Identity "pvalencia"

## 3. Unlock user
### ADAC Method
- Locate the user
- Right-click → Reset Password
- Set a new temporary password
- Ensure User must change password on next logon radial is selected
- Ensure unlock users' account radial is selected

### Powershell Equivalent
- Unlock-ADAccount -Identity amasters
- Set-ADAccount -Identity 'amasters' -Reset -NewPassword (ConvertTo-SecureString -AsPlaintext "NewP@ssswordReset!" -Force)
- Set-ADUser -Identity amasters -ChangePasswordatlogon $true

---
## 4. Create an OU and Add a Group
### ADAC Method
- Right-click IT OU → New → Organizational Unit
- Name the OU Security Analysts
- Right-click on the Security Analysts OU → New → Group
- Name the Group Security Analysts
- Ensure the Group Scope is set to "Domain Local" and the Group Type is set to "Security"

### Powershell Equivalent
- New-ADOrganizationUnit -Name "Security Analysts" -Path "OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=inlanefreight,DC=local"
- New-ADGroup -Name "Security Analysts" -SamAccoutName analyst -Groupcategory Security GroupScope Global -DisplayName "Security Analysts" -Path "OU= Security Analysts,OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=inlanefreight,DC=local" -Descritption "Members of this group are Security Analysts under the IT OU."

---
## 5. Add Users to the Group
### ADAC Method
- Locate users to add to the group
- Right-click user → Add to Group → Specify Group

###Powershell Equivalent
Add-ADGroupMember -Identity analysts -Members ACastillo, ACepheus, OStarchaser

--- 

## 6. Apply Group Policy to the OU using Powershell and Modify User Configurations via GPMC
### PowerShell
- Copy-GPO -SourceName "Logon Banner" -TargetName "Security Analysts Control"
- New-GPLink -Name "Security Analysts Control" -Target "OU= Security Analysts,OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=inlanefreight,DC=local" -LinkEnabled yes

### ADAC / GPMC Method
- Open Group Policy Management Console
- Navigate to Securty Analysts Contol
- Navigate to Removable storage access → Right-click All Removable Storage classess:Deny all access → Edit → Enable this configurations
- Navigate to System → Right-click Prevent Access to Command prompt → Edit → Disable
- Navigate to Interactive logon message text and interactive logon Message title → Right-click → Edit → Select Define Policy radial→ Define Policies
- Navigate to Password Policy → Right-click Minimum Password length, Minimum Password Age, etc. → Properties → Select Define policy radial → Define policy

--- 

## 7. Adding a Remote computer to a domain & Moving to a New OU
### ADAC Method
- Navigate to the Control Panel → System and Security → System → Change settings
- Select the "Change" radial to rename the computer or change its domain. 
- Enter the name of the Domain → Select ok → Enter credentials of an account that has permission join the computer to the domain
- Open ADAC → Navigate to the Computers OU → Right-click the newly added computer → Select move
- Move the computer to the Security Analysts OU we created.

### Powershell Equivalent
- Add-Computer -ComputerName ACADEMY-IADD-W10 -LocalCredentials ACADEMY-IAD-W10/image -DomainName INLANEFREIGHT.LOCAL -Credential INLANEFREIGHT\htb-student_adm -Restart
- Get-ADComputer -Identity "ACADEMY-IAD-W10" -Properties * | select CN,CanonicalName, IPv4Address


---

## Result
Completed the lab with a full understanding of Active Directory fundamentals and its importance in networked environments. The experience strengthened my ability to work in AD-supported enterprise systems, a critical skill for IT Support and SOC roles.

---

## Let’s Connect
I'm seeking entry-level roles in **IT Support**, **SOC Analysis**, or **Security Operations** where I can apply my AD knowledge and hands-on cybersecurity skills.

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)





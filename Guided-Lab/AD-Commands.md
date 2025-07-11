# Active Directory PowerShell Commands & Explanations

This document outlines all PowerShell commands used throughout the **Foundations of Active Directory** lab. Each command includes a clear explanation of its purpose and context.

---

## 1. Create a New AD User
```powershell
New-ADUser -Name "Artemis Castillo" -AccountPassword (ConvertTo-SecureString -AsPlainText (Read-Host "Enter Secure Password" -Force) -Enabled $true -OtherAttributes @{`title`= "Analyst"; `mail`= "a.castillo@inlanefreight.local} `
```
**Explanation:** Creates a user object in the specified OU with a secure password and relevant attributes.

---

## 2. Remove a User
```powershell
Remove-ADUser -Identity "pvalencia"
```
**Explanation:** Deletes a user with the specified `sAMAccountName` or distinguished name.

---

## 3. Unlock and Reset Password for a User
```powershell
Unlock-ADAccount -Identity amasters
```
```powershell
Set-ADAccountPassword -Identity 'amasters' -NewPassword (ConvertTo-SecureString "NewP@ssswordReset!" -AsPlainText -Force)
```
```powershell
Set-ADUser -Identity amasters -ChangePasswordAtLogon $true
```
**Explanation:** Unlocks a locked account, resets the password, and forces a password change at next login.

---

## 4. Create an Organizational Unit (OU)
```powershell
New-ADOrganizationalUnit -Name "Security Analysts" -Path "OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=INLANEFREIGHT,DC=local"
```
**Explanation:** Creates a new OU nested within the defined structure.

---

## 5. Create a Security Group
```powershell
New-ADGroup -Name "Security Analysts" -SamAccountName "analyst" -GroupCategory Security -GroupScope Global -DisplayName "Security Analysts" -Path "OU=Security Analysts,OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=INLANEFREIGHT,DC=local" -Description "Members of this group are Security Analysts under the IT OU."
```
**Explanation:** Creates a security group within the Security Analysts OU for access control.

---

## 6. Add Users to a Group
```powershell
Add-ADGroupMember -Identity "analyst" -Members ACastillo, ACepheus, OStarchaser
```
**Explanation:** Adds multiple users to the specified group.

---

## 7. Copy a Group Policy Object (GPO) and Apply to OU
```powershell
Copy-GPO -SourceName "Logon Banner" -TargetName "Security Analysts Control"
```
```powershell
New-GPLink -Name "Security Analysts Control" -Target "OU=Security Analysts,OU=IT,OU=HQ-NYC,OU=Employees,OU=Corp,DC=INLANEFREIGHT,DC=local" -LinkEnabled Yes
```
**Explanation:** Copies an existing GPO and links it to a new OU.

---

## 8. Add a Remote Computer to a Domain
```powershell
Add-Computer -ComputerName ACADEMY-IAD-W10 -LocalCredential ACADEMY-IAD-W10\image -DomainName INLANEFREIGHT.LOCAL -Credential INLANEFREIGHT\htb-student_adm -Restart
```
**Explanation:** Joins a remote computer to the specified domain.

---

## 9. View Computer Properties
```powershell
Get-ADComputer -Identity "ACADEMY-IAD-W10" -Properties * | Select CN, CanonicalName, IPv4Address
```
**Explanation:** Retrieves and displays selected properties for a domain-joined computer.

---

## Tip:
Use `Get-Help <CommandName> -Examples` for more use cases or run `Import-Module ActiveDirectory` if AD commands are unavailable.

---

*[Back to Main Project](../README.md)*

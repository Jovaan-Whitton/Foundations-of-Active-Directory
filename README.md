# active-directory-basics-htb
Hands-on Active Directory lab from Hack The Box. Explored domain structures, user and group enumeration, and Windows authentication flows in a simulated enterprise environment. Practiced privilege mapping and identified common AD misconfigurations relevant to IT and security support roles

# Intro to Active Directory – Hack The Box

## Project Overview
This lab introduced me to the fundamentals of **Active Directory (AD)** within a simulated Windows enterprise environment. Through hands-on exercises, I explored domain structures, authentication processes, user enumeration, and common security misconfigurations. The project mirrors real-world AD environments used in corporate networks and lays the groundwork for both blue team and red team perspectives.

---

## Objectives
- Understand the structure of Active Directory and how domain components are organized
- Perform enumeration of users, groups, and domain controllers
- Explore AD authentication flows and permission hierarchies
- Identify typical attack surfaces in AD environments

---

## Tools & Technologies
- **Platform**: Hack The Box Academy  
- **Tools Used**: Windows Command Line, PowerShell, BloodHound (Intro), `net` commands, `whoami`, `nltest`, `dsquery`  
- **Environment**: Simulated Windows Domain Environment  
- **Skills Practiced**: AD Enumeration, Group Policy Basics, Access Mapping

---

## Steps Taken

1. **Initial AD Reconnaissance**
   - Used commands like `net user /domain`, `nltest /dclist`, and `whoami /all` to explore domain details
   - Identified domain users, groups, and the domain controller (DC)

2. **Group and Permission Discovery**
   - Enumerated built-in security groups and administrative privileges
   - Mapped relationships between users and groups

3. **Authentication Understanding**
   - Explored how Kerberos and NTLM authentication operate in AD
   - Reviewed token privileges, impersonation, and SID structures

4. **Intro to Security Posture**
   - Identified potentially misconfigured users or groups
   - Examined how AD structure can be abused if not properly secured

---

## Key Skills & Learnings
- Developed working knowledge of AD layout and command-line interaction
- Practiced user and group enumeration to support identity auditing
- Gained foundational understanding of Windows domain authentication
- Identified risks that arise from excessive privileges or weak group policy

---

## Screenshots
> Store images in a `screenshots/` folder:

- ![AD User Enumeration](screenshots/net-user-domain.png)
- ![Group Membership](screenshots/group-membership.png)
- ![DC Identification](screenshots/domain-controller.png)

---

## Files Included
- `ad-commands.md` – List of commands used with explanations  
- `domain-findings.md` – Summary of users, groups, and DCs discovered  
- `screenshots/` – Visual walkthrough of key steps

---

## Result
Completed the lab with a full understanding of Active Directory fundamentals and its importance in networked environments. The experience strengthened my ability to work in AD-supported enterprise systems, a critical skill for IT Support and SOC roles.

---

## Let’s Connect
I'm seeking entry-level roles in **IT Support**, **SOC Analysis**, or **Security Operations** where I can apply my AD knowledge and hands-on cybersecurity skills.

**Email**: jovaan.jwhitton@gmail.com  
**LinkedIn**: [linkedin.com/in/jovaan-whitton-profile](https://linkedin.com/in/jovaan-whitton-profile)

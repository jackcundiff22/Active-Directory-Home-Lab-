
# Active Directory Home Lab (Windows Server 2022)

##  Overview

This project is a hands-on Active Directory home lab built in a virtualized Windows Server 2022 environment. The goal was to simulate a small business IT infrastructure by configuring identity management, access control, shared resources, and user policy enforcement.

This lab demonstrates practical IT support and systems administration skills relevant to Help Desk, Desktop Support, Junior Systems Administration, and entry-level Infrastructure roles.

---

## Project Objectives

The purpose of this lab was to simulate a small business IT environment and practice common system administration tasks, including:

* Deploying and organizing Active Directory users, groups, and OUs
* Applying group-based permissions to shared resources
* Enforcing security policies with Group Policy
* Automating user resource access through mapped network drives
* Testing user access and security restrictions across multiple roles

##  Technologies Used

* Windows Server 2022 (GUI)
* Active Directory Domain Services (AD DS)
* Group Policy Management (GPO)
* NTFS Permissions
* VirtualBox (Virtualization)
* Windows File Sharing (SMB)

---

##  Environment Setup

* Created a domain: `helpdesk.local`
* Promoted server to Domain Controller
* Built Organizational Units (OUs) for departments:

  * HR
  * Finance
  * IT
  * Interns

---

## Lab Scenario

This lab simulates a small company with multiple departments, each requiring separate access to files and resources.

The environment was designed so that:

* HR staff can access HR documents only
* Finance staff can access Finance files only
* IT staff can support systems and access IT resources
* Interns have limited access and additional restrictions

This setup reflects a basic real-world business environment where user access must be controlled based on job role.

##  User & Group Management

* Created domain users:

  * HR User
  * Finance User
  * IT User (JackUser)
  * IT Admin (JackAdmin)
  * Intern User
* Implemented **security groups**:

  * HR_Team
  * Finance_Team
  * IT_Users
  * IT_Admins
  * Interns_Limited

✔ Used **group-based access control instead of assigning permissions directly to users**

---

##  File Shares & Permissions

Created shared folders for each department:

* HR
* Finance
* IT
* Interns

Configured:

* Share Permissions
* NTFS Permissions

✔ Enforced **department-based access control**
✔ Implemented **least privilege principle**

Examples:

* HR users can only access HR files
* Finance users can only access Finance files
* Intern users have restricted access
* IT users have broader access for support

---

##  Security & Group Policy

Configured domain-wide policies:

* Password Policy (complexity, length, expiration)
* Account Lockout Policy

Created custom GPO:

### Intern Restrictions

* Disabled Command Prompt
* Blocked Control Panel / Settings access

✔ Demonstrates **role-based security enforcement**

---

##  Drive Mapping (User Environment Automation)

Used Group Policy to automatically map network drives:

* HR → `H:` drive
* Finance → `F:` drive
* IT → `I:` drive

✔ Users receive appropriate resources automatically upon login

---

##  Testing & Validation

Tested each user role to verify correct behavior:

### HR User

* Access to HR only
* Denied access to Finance and IT

### Finance User

* Access to Finance only
* Denied access to HR and IT

### IT Users

* Access to IT resources
* Elevated access depending on role

### Intern User

* Limited access
* Read-only restrictions
* Command Prompt and Control Panel blocked via GPO

✔ Validation included:

* Successful user authentication to the domain
* Correct department-based file access
* Denied access to unauthorized shares
* Successful network drive mapping at login
* GPO restrictions applied correctly to limited users
* File edit/save testing within permitted folders

---

##  Key Concepts Demonstrated

* Active Directory structure (OUs, users, groups)
* Role-Based Access Control (RBAC)
* Least Privilege Security Model
* Group Policy Management
* NTFS vs Share Permissions
* Network Drive Mapping via GPO
* User access troubleshooting

---

##  Screenshots

Examples:

<h3>Active Directory Structure</h3>
<img src="https://github.com/user-attachments/assets/fc9b4cd1-0323-4431-9a7b-435b8beb8537" width="800"/>

<h3>Folder Permissions</h3>
<img src="https://github.com/user-attachments/assets/a88daa1a-c9df-4ef5-bedc-be2094869363" width="800"/>

<h3>Mapped HR Drive</h3>
<img src="https://github.com/user-attachments/assets/148cd1f4-eaf9-4465-ba4b-2e8f21fd37eb" width="800"/>

<h3>Access Denied Validation</h3>
<img src="https://github.com/user-attachments/assets/46aa4afa-9f6a-4352-af59-ef6019c832a4" width="800"/>


---

##  Skills Demonstrated

* Windows Server Administration
* Active Directory Management
* User & Group Administration
* File Share Configuration
* Security Policy Implementation
* Troubleshooting & Validation
* IT Support Fundamentals

---

## What I Learned

Through this lab, I gained hands-on experience with several core IT administration concepts, including:

* How Active Directory organizes users and resources in a business environment
* Why security groups are better than assigning permissions directly to users
* The difference between NTFS permissions and share permissions
* How Group Policy can automate configuration and restrict user behavior
* How to validate access controls by testing from the end-user perspective

This project also helped me better understand how IT support and system administration overlap in real-world environments.

##  Future Improvements

* Add Windows 10/11 client machine joined to domain
* Simulate help desk ticket scenarios
* Implement additional GPO restrictions
* Explore Microsoft Entra ID / cloud identity integration

---

##  Summary

This project demonstrates practical, hands-on experience with core IT infrastructure and support concepts. It reflects the type of tasks performed in real-world IT environments, particularly in help desk and system administration roles.

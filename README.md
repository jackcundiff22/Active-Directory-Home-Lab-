
# Active Directory Home Lab (Windows Server 2022)

##  Overview

This project is a hands-on Active Directory home lab built using Windows Server 2022 in a virtualized environment. The goal was to simulate a real-world enterprise IT environment by configuring domain services, user management, access control, Group Policy, and network file sharing.

This lab demonstrates core IT support and system administration skills relevant to Help Desk, Desktop Support, and Junior IT roles.

---

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

✔ Verified:

* Authentication (login works)
* Authorization (correct access levels)
* Policy enforcement (restrictions applied)

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



Example:
![Active Directory Structure] <img width="1918" height="1078" alt="active-directory-ous" src="https://github.com/user-attachments/assets/fc9b4cd1-0323-4431-9a7b-435b8beb8537" />

![Group Policy Permissions] <img width="1918" height="1078" alt="it-folder-permissions-security" src="https://github.com/user-attachments/assets/a88daa1a-c9df-4ef5-bedc-be2094869363" />

![Mapped Drives] <img width="1911" height="1072" alt="hr-drive" src="https://github.com/user-attachments/assets/148cd1f4-eaf9-4465-ba4b-2e8f21fd37eb" />

![Access Denied Example] <img width="1907" height="1073" alt="hr-user-denied" src="https://github.com/user-attachments/assets/46aa4afa-9f6a-4352-af59-ef6019c832a4" />


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

##  Future Improvements

* Add Windows 10/11 client machine joined to domain
* Simulate help desk ticket scenarios
* Implement additional GPO restrictions
* Explore Microsoft Entra ID / cloud identity integration

---

##  Summary

This project demonstrates practical, hands-on experience with core IT infrastructure and support concepts. It reflects the type of tasks performed in real-world IT environments, particularly in help desk and system administration roles.

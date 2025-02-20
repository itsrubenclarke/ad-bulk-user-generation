<p align="center">
<img src="https://github.com/user-attachments/assets/ea8315b8-28f8-4d0a-a370-917bdc1c56f3" height="30%" width="50%" alt="Microsoft Azure Logo"/>
</p>

<h1>Active Directory: Bulk User Generation</h1>

<p> 
This project is the third in a collection focused on implementing Azure and Active Directory. The goal here focuses on configuring Remote Desktop access and user management within an Azure-based Active Directory environment. 
I will start by powering on the DC-1 and client-1 VMs, then enable Remote Desktop for non-administrative users on client-1. 
Using the "jane_admin" account, I will allow domain users remote access, enabling standard user logins. 
Next, I will create multiple user accounts via PowerShell on DC-1, verify them in Active Directory Users and Computers under the _EMPLOYEES Organisational Unit. 
Then test logins on client-1 with these new accounts. This setup simulates user management and remote access configuration in a domain environment.
</p>

<h2>Prerequisites</h2>

- <a href="https://github.com/itsrubenclarke/active-directory-vm-deployment"> Active Directory: Virtual Machine Deployment </a>
- <a href="https://github.com/itsrubenclarke/ad-install-and-config"> Active Directory: Installation and Configuration </a>

<h2>Key Objectives</h2>

<p>
  <h3>Setup RDP for non-adminstrative users on client-1</h3>
  
  -  Log into client 1 as Domain Admin and enable Remote Desktop Access 
</p>

<p>
  <h3>User Creation</h3>
  
  -  Create multiple Active Directory users with a PowerShell Script
</p>

<h3>Environments and Technologies Used</h3>

- Microsoft Azure (Virtual Machines, Networking)
- Windows App (Remote Desktop Protocol)
- Active Directory (Domain Services)
- PowerShell (Command-line Operations)

<p>
  <h3>Operating Systems Used</h3>
</p>

| **Operating System**        | **Role**               
|----------------------------|------------------------|
| <img alt= "windows logo" src="https://i.imgur.com/KcrV0u6.png" width="20"> Windows (Windows 10 Pro) | Client VM |
| <img alt= "Windows logo" src="https://i.imgur.com/KcrV0u6.png" width="20"> Windows (Server 2022) | Domain Controller (DC)             |



<h1>Remote Desktop Connection</h1>


<h3><img alt= "RDP logo" src="https://github.com/user-attachments/assets/4aaa5d6e-ce8b-481f-a8da-57edc9a2917e" width="20"> Step 1: Establish Remote Desktop Connection</h3>

- Launch your Remote Desktop Connection Application
    - Mac Users download <a href="https://apps.apple.com/us/app/windows-app/id1295203466?mt=12" target="_blank" rel="noopener noreferrer">Windows App</a> Formerly known as "Microsoft Remote Desktop"
    - Windows Users open and use Remote Desktop
- Select "Add PC"
- Select the "client-1" VM you created earlier
- Log in as "mydomain.com\jane_admin"
- Open "System Properties"
- Click "Remote Desktop"
- Allow "domain users" access to remote desktop

<h3>Step 2: Bulk User Creation</h3>

- Launch your Remote Desktop Connection Application
    - Mac Users download <a href="https://apps.apple.com/us/app/windows-app/id1295203466?mt=12" target="_blank" rel="noopener noreferrer">Windows App</a> Formerly known as "Microsoft Remote Desktop"
    - Windows Users open and use Remote Desktop
- Select "Add PC"
- Select the "dc-1" VM you created earlier
- Log in as "jane_admin"
- Open "PowerShell" as an administrator
- Create a new File and paste the contents of <a href="https://github.com/itsrubenclarke/AD-PS/blob/main/Generate-Names-Create-Users.ps1">this</a> script
- Run the script and observe the accounts being created
- Once complete open the Active Directory ?? and confirm the accounts are in the appropriate organisational unit "_EMPLOYEES"
- Attempt to log into "client-1" with one of the acccounts using the password that was present in the <a href="https://github.com/itsrubenclarke/AD-PS/blob/main/Generate-Names-Create-Users.ps1">script</a> "Password1"


<h1>Project Summary</h1></p>

🎉Congratulations! You configured RDP access and managed Active Directory users in Azure!🎉

In this project, you established Remote Desktop connections to both a Windows 10 Pro Client VM (client-1) and a Windows Server 2022 Domain Controller (dc-1) using RDP. You enabled Remote Desktop access for non-administrative users on client-1 by allowing domain users access through system properties. Then, using PowerShell on dc-1, you created multiple Active Directory user accounts in bulk and verified them in the "_EMPLOYEES" organisational unit. Finally, you tested user logins on client-1 some of the newly created accounts, successfully managing user access within the Azure-based Active Directory environment.

  


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
  <h3>Setup RDP for non-administrative users on client-1</h3>
  
  -  Log into client-1 as Domain Admin and enable Remote Desktop Access 
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
- Click the text linked below "User Accounts"
- Click "Add"
- Enter "domain users"
- Click "Check Names"
- Click "OK"
- Should should now see "MYDOMAIN\Domain Users" listed in the Remote Desktop Users window

<img width="1788" alt="client-1 Login" src="https://github.com/user-attachments/assets/569b3f89-0742-4a42-8f0a-f186d524a405" />
<img width="1790" alt="System - remote desktop" src="https://github.com/user-attachments/assets/bda1c317-d5d5-4e73-b876-184a8d288449" />
<img width="1788" alt="Add Domain Users" src="https://github.com/user-attachments/assets/cd1d938f-f988-4554-a493-f932bed35b0c" />


<h3>Step 2: Bulk User Creation</h3>

- Launch your Remote Desktop Connection Application
    - Mac Users download <a href="https://apps.apple.com/us/app/windows-app/id1295203466?mt=12" target="_blank" rel="noopener noreferrer">Windows App</a> Formerly known as "Microsoft Remote Desktop"
    - Windows Users open and use Remote Desktop
- Select "Add PC"
- Select the "dc-1" VM you created earlier
- Log in as "jane_admin"
- Open "PowerShell_ISE" as an administrator
- Create a new File and paste the contents of <a href="https://github.com/itsrubenclarke/AD-PS/blob/main/Generate-Names-Create-Users.ps1">this</a> script
- Run the script and observe the accounts being created
- Once complete open the "Active Directory Users and Computer" and confirm the accounts are in the appropriate organisational unit "_EMPLOYEES"
- Log out of "client-1" using the "logoff" command
- Attempt to log into "client-1" with one of the acccounts using the password that was present in the <a href="https://github.com/itsrubenclarke/AD-PS/blob/main/Generate-Names-Create-Users.ps1">script</a> "Password1"


<img width="1788" alt="dc-1 Login" src="https://github.com/user-attachments/assets/83a0cedb-a35c-491a-83d2-9cf9544390db" />
<img width="1790" alt="Run Powershell ISE" src="https://github.com/user-attachments/assets/efba5bfa-43d2-4a3f-b4da-e47a4e9740e5" />
<img width="1788" alt="File - New" src="https://github.com/user-attachments/assets/422201ed-1ad5-44d6-8b41-2a783a07a8e0" />
<img width="1787" alt="Paste Script" src="https://github.com/user-attachments/assets/b0c323ac-02a4-442f-9b5b-a7437e0c8f85" />
<img width="1790" alt="Run Script" src="https://github.com/user-attachments/assets/76e5170a-759a-4af3-b90b-f66db0777984" />
<img width="1791" alt="Ad users and computers" src="https://github.com/user-attachments/assets/ad3c0dc8-08a5-4378-969a-871053f22fed" />
<img width="1789" alt="image" src="https://github.com/user-attachments/assets/4dc9a37a-3ccf-41ac-9dbc-b2ebe5c28ddf" />
<img width="1788" alt="bag.bub Login" src="https://github.com/user-attachments/assets/43c95d5a-5781-4da0-91bc-4b79f187873e" />
<img width="1791" alt="Successful Login" src="https://github.com/user-attachments/assets/5aabb9fd-1d56-42eb-b42a-10cccf911904" />















<h1>Project Summary</h1></p>

🎉Congratulations! You configured RDP access and managed Active Directory users in Azure!🎉

In this project, you established Remote Desktop connections to both a Windows 10 Pro Client VM (client-1) and a Windows Server 2022 Domain Controller (dc-1) using RDP. You enabled Remote Desktop access for non-administrative users on client-1 by allowing domain users access through system properties. Then, using PowerShell on dc-1, you created multiple Active Directory user accounts in bulk and verified them in the "_EMPLOYEES" organisational unit. Finally, you tested user logins on client-1 some of the newly created accounts, successfully managing user access within the Azure-based Active Directory environment.

  


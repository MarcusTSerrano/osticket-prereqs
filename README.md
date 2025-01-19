<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro </b> (22H2), at least 2vCPUs, 8GB RAM

<h2>List of Prerequisites</h2>

- <b>PHP manager for IIS</b> - ensures PHP is correctly configured to run IIS
- <b>Rewrite module </b> - facilitates URL rewriting and redirect users to URLs
- <b>VC_redist.x86</b> (redistributable) - osTicket relies on libraries that are part of Microsoft Visual C++ and ensures the program runs smoothly
- <b>MySQL</b> - for storing data into databases
- <b>HeidiSQL</b> - interface for accessing MySQL 



<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DSBoJG6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/T0XQ8qI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Create a Virtual Machine
  </p>
Name : Vm-osTicket
</p>
Image : Windows 10 Pro, version 22H2
</p>
Size : Standard D2s v3 - 2 vcpus, 8 GiB memory
</p>
Username : Labuser
</p>
Password : LabPassword1
</p>
Make sure to select the boxx under Licensing
</p> 
Create the VM with no further changes
</p>
<br />


<p>
<img src="https://i.imgur.com/DPqmqvQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Connect to the VM usind the public IP address in Remote Desktop Connection (RDP)
</p>
<br />

<p>
<img src="https://i.imgur.com/Jaz4Z4B.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter your credentials
</p>
<br />

<p>
<img src="https://i.imgur.com/uoPvrBH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Control Panel > Programs > Programs and Features
</p>
Select Turn Windows features on or off
</p>
Install / Enable IIS in Windows WITH CGI
</p>
World Wide Web Services -> Application Development Features -> [X] CGI ( ‼️CGI Needs to be selected‼️)
</p>
<br />

<p>
<img src="https://i.imgur.com/W0EdANl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
</p>
 https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD
 </p>
<br />

<p>
<img src="https://i.imgur.com/jVfmBer.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img src="https://i.imgur.com/aQaa4uq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />

<p>
<img src="https://i.imgur.com/LDyP4VO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/E1XinZy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
</p>
<br />

<p>
<img src="https://i.imgur.com/49j6E5z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe. 
</p>
<br />

![image](https://github.com/user-attachments/assets/bae3f9b6-8dce-41e7-9f13-a37241a4caa6)

<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  </p>
Typical Setup
</p>

![image](https://github.com/user-attachments/assets/71b0822b-a309-4439-80c1-150c9c9dd546)

Launch Configuration Wizard (after install)
</p>

![image](https://github.com/user-attachments/assets/4f249108-050d-49c0-9125-ba07d1c9efab)

Standard Configuration
</p>

![image](https://github.com/user-attachments/assets/bcbc57aa-dc9f-4fe6-9a77-16c974180251)

Username: root
</p>
Password: root
</p>

![image](https://github.com/user-attachments/assets/458f07a3-d5ba-4288-99dc-1ba2b884549a)

Finish Installation
</p>
<br />

![image](https://github.com/user-attachments/assets/61d905cc-03c6-4f83-b4ce-13181e233d46)

<p>
Open IIS as an Admin
</p>
<br />

![image](https://github.com/user-attachments/assets/4235db7a-b7e1-4d33-8a30-3ba386418c0f)

<p>
Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
</p>
<br />

![image](https://github.com/user-attachments/assets/c1e7bc26-a464-4a32-8f8b-ad75126c0c34)

![image](https://github.com/user-attachments/assets/0f7b5be8-f1c4-43a2-8f6d-85b791191857)

<p>
Reload IIS (Right-click in VM-osTicket Home, Stop and Start the server) ‼️Important to do, Server needed to restart after Regestration‼️
</p>
<br />

![image](https://github.com/user-attachments/assets/e6f8bf0b-0e5d-464e-904d-e0a67f2c57a1)
![image](https://github.com/user-attachments/assets/6169bcf1-29b3-4cb5-bcc1-7dc2ae6977b1)

<p>
Install osTicket v1.15.8
  </p>
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
</p>
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
</p>
<br />

![image](https://github.com/user-attachments/assets/c1e7bc26-a464-4a32-8f8b-ad75126c0c34)

![image](https://github.com/user-attachments/assets/0f7b5be8-f1c4-43a2-8f6d-85b791191857)

<p>
Reload IIS (Right-click in VM-osTicket Home, Stop and Start the server) ‼️Important to do, Server needs to restart after the installation‼️
</p>
<br />

![image](https://github.com/user-attachments/assets/ad4be1a4-5f0a-43cd-88e9-0c800caab0fb)

<p>
Go to sites -> Default -> osTicket
</p>
On the right, click “Browse *:80”
</p>
<br />

![image](https://github.com/user-attachments/assets/daccd225-1f6a-489b-9f96-3638ff901485)

<p>
Note that some extensions are not enabled
</p>
<br />

![image](https://github.com/user-attachments/assets/62bf4222-2463-4221-aff1-63f6c8cbcd22)

<p>
Go back to IIS, sites -> Default -> osTicket
</p>
Double-click PHP Manager 
</p>

![image](https://github.com/user-attachments/assets/4ffd79f1-3fa4-4753-a0db-feeae67e840d)

<p>
Click “Enable or disable an extension” 
</p>

![image](https://github.com/user-attachments/assets/b43e7cc2-e7a5-473e-b4b8-a322b44d281e)

Enable: php_imap.dll
</p>

![image](https://github.com/user-attachments/assets/514b2f15-bb16-4d76-838f-c3a841ca50ea)

Enable: php_intl.dll
</p>

![image](https://github.com/user-attachments/assets/4cb3339d-0af2-4ccb-95a8-943b8f3b467c)

Enable: php_opcache.dll
</p>

![image](https://github.com/user-attachments/assets/99510ce3-9b7d-4fb9-8c46-c10fc59f5e04)

<p>
Refresh the osTicket site in your browser
</p>
<br />

![image](https://github.com/user-attachments/assets/d5c8d0c1-4ca7-4f2c-b3a6-f0c8cb96530f)

<p>
Observe the changes
</p>
<br />

![image](https://github.com/user-attachments/assets/7e37823d-4e69-4fd5-bebf-72a581708d64)

![image](https://github.com/user-attachments/assets/30379256-6a93-4a0b-81d7-e7a5934ce279)

<p>
This PC > Windows (C:) > inetpun > wwwroot > osTicket > include > Rename: "ost-sampleconfig.php" to "ost-config.php"
</p>
<br />

![image](https://github.com/user-attachments/assets/2da692bd-d257-4876-8b06-9aad3f8901a4)

<p>
Right-click "ost-config.php" - select "Properties"
</p>
<br />

![image](https://github.com/user-attachments/assets/1db73958-991d-46e0-a98f-22919dd8a9e8)

<p>
Under "Security" select "Advanced"
</p>
<br />

![image](https://github.com/user-attachments/assets/dd1ffeca-ba98-4f1f-b2ee-9f6ae6d28162)

<p>
Disable inheritance - Remove All
</p>
<br />

![image](https://github.com/user-attachments/assets/c3659b8c-25b4-4175-9b7c-165212962e42)

<p>
Add New Permissions
</p>

![image](https://github.com/user-attachments/assets/096add8c-55e1-4530-b78c-92292916ad2d)

<p>
Select a Principal
</p>

![image](https://github.com/user-attachments/assets/cb2e1f38-cd35-42b6-852b-c43faff489a7)

<p>
Everyone
</p>

![image](https://github.com/user-attachments/assets/1f8e6c1c-71f1-497e-af70-24d5ba2bb3d7)

<p>
Full Control
</p>

![image](https://github.com/user-attachments/assets/9d3b619d-abff-4253-b55c-863318c1faa3)

<p>
Apply changes
</p>
<br />

![image](https://github.com/user-attachments/assets/a6193ca7-39ea-4fd6-8d48-a97f7cce78e9)

<p>
Continue Setting up osTicket in the browser (click Continue)
</p>
<br />

![image](https://github.com/user-attachments/assets/c1b5d778-a73d-4a96-b83f-fd4a30974fef)

<p>
From the “osTicket-Installation-Files” folder, install HeidiSQL ( No changes necessary )
</p>
<br />

![image](https://github.com/user-attachments/assets/5a6f67a4-f663-4a9a-b303-946adaedecb3)

<p>
Launch Heidi SQL
</p>
<br />

![image](https://github.com/user-attachments/assets/b7370a77-cf25-4185-b01e-486108b9607b)

<p>
Create a new session, root/root
</p>
<br />

![image](https://github.com/user-attachments/assets/d74156a5-d67c-4569-83d4-f70f3cbade06)

<p>
Connect to the session
</p>
<br />

![image](https://github.com/user-attachments/assets/f9c6707b-0f38-4556-a426-e1038a352ca3)

<p>
Create a database
</p>

![image](https://github.com/user-attachments/assets/5774a997-afdf-4a90-bd37-ee7846284b70)

<p>
Name the database “osTicket”
</p>

![image](https://github.com/user-attachments/assets/9e1b6793-da95-4c04-ad26-a040d48bc975)

<p>
View database
</p>
<br />

![image](https://github.com/user-attachments/assets/56e54aa0-db68-4675-a55f-edffee9b9e02)

<p>
Continue Setting up osTicket in the browser
</p>
Name Helpdesk
</p>
Default email (receives email from customers)
</p>
Fill in Admin User
</p>
Email Addresses needs to be different from Default email
</p>
Username : Adminuser
</p>
Password : Password1
</p>
Fill in Database Settings
</p>
MySQL Database: osTicket
</p>
MySQL Username: root
</p>
MySQL Password: root
</p>
Click “Install Now!”
</p>

</p>

<br />


<p>
Lorem ipsum dolor sit amet,
</p>
<br />


<p>
Lorem ipsum dolor sit amet,
</p>
<br />

<p>
Lorem ipsum dolor sit amet,
</p>
<br />


<p>
Lorem ipsum dolor sit amet,
</p>
<br />

<p>
Lorem ipsum dolor sit amet,
</p>
<br />


<p>
Lorem ipsum dolor sit amet,
</p>
<br />
























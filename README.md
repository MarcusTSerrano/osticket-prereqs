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
Reload IIS (Right-click in VM-osTicket Home, Stop and Start the server) 
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


























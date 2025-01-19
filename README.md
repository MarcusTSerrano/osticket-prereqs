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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  </p>
Typical Setup
</p>
Launch Configuration Wizard (after install)
</p>
Standard Configuration
</p>
Username: root
</p>
Password: root
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, 
</p>
<br />


























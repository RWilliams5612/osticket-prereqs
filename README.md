
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

 ### [YouTube Demonstration](https://www.youtube.com)

<h2>Description</h2>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />
<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

This tutorial outlines the prerequisites and installation of oS TICKET.
---------------------------------

Create an Azure Virtual Machine Windows 10, 4 vCPUs
![2024-11-15_07h50_33](https://github.com/user-attachments/assets/47e5d75b-4a95-4d73-9d8b-0952d5a8a300)


Log into the VM with Remote Desktop

Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.
![2024-11-15_07h56_19](https://github.com/user-attachments/assets/23946b03-75c0-4728-a198-05fa7a5e5e86)


Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI
![2024-11-15_08h01_05](https://github.com/user-attachments/assets/78170219-778b-4709-9fd5-a2968e6236fa)

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
![2024-11-15_08h06_31](https://github.com/user-attachments/assets/269b5ee1-c18d-476b-aac0-3b4f9c3c8506)


From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
![2024-11-15_08h12_10](https://github.com/user-attachments/assets/c8eaab46-b53a-4dfb-b6fa-7fbab977d6b2)


Create the directory C:\PHP
![2024-11-15_08h14_24](https://github.com/user-attachments/assets/a429d57a-18ee-4c0a-9cca-6733eea075ed)


From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder



*From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

*From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

*From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root

*Open IIS as an Admin

*Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

*Reload IIS (Open IIS, Stop and Start the server)

*Install osTicket v1.15.8
*From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
*Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

*Reload IIS (Open IIS, Stop and Start the server)

*Go to sites -> Default -> osTicket
*On the right, click “Browse *:80”

*Note that some extensions are not enabled
*Go back to IIS, sites -> Default -> osTicket
*Double-click PHP Manager
*Click “Enable or disable an extension”
*Enable: php_imap.dll
*Enable: php_intl.dll
*Enable: php_opcache.dll
*Refresh the osTicket site in your browser, observe the changes

*Continue Setting up osTicket in the browser (click Continue)
*Name Helpdesk
*Default email (receives email from customers)

*From the “osTicket-Installation-Files” folder, install HeidiSQL.
*Open Heidi SQL
*Create a new session, root/root
*Connect to the session
*Create a database called “osTicket”

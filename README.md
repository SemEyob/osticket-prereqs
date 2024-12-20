
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Outline of prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2> What is osTicket? </h2>

osTicket is an open-source help desk and ticketing system that efficiently manages customer support. It features ticket management, customizable forms, agent collaboration, automated workflows, a knowledge base, and reporting tools. osTicket supports email integration, multiple languages, and role-based access control, with free and professional support options.

<h2> Overview </h2>

Create a Virtual Machine running Windows 10 in Azure. To ensure consistency, install osTicket and necessary dependencies. The steps include enabling IIS with specific features, installing PHP Manager and the Rewrite Module, setting up PHP 7.3.8, MySQL 5.5.62, and configuring osTicket. We will then finalize the setup by configuring the necessary PHP extensions and setting up the database. Lastly, clean up by securing configuration files and setting appropriate permissions.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- IIS and Management Console
- PHP and Rewrite Module 
- MySQL
- HeidiSQL
- osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/vvoU3a4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Create a virtual machine that uses Windows 10.
- Install IIS by right-clicking on the start button, click on "run" and type in "control panel".
- Select program and features. Select "windows features". Install and enable IIS management console in web management tools.
- In addition, enable CGI and all of Common HTTP Features boxes (located in: world wide web services > application development features.)
- Install PHP manager.
- Install rewrite module.
  </p>

<br />

<p>
<img src="https://i.imgur.com/McWbPOj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Create a folder in C:\ called "PHP".
- Install PHP and unzip contents to PHP folder that was created.
- Install VC redist.x86.exe. Install MySqL (typical setup).
- Launch configuration wizard, select standard and create a name plus password. FYI- Take note of password, as it will be needed.</p>
<br />

<p>
<img src="https://i.imgur.com/gEEG4Ae.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Open IIS as administrator.
- Register PHP inside of IIS.
- Stop and start server.
- Install osTicket.
- Extract "uploads" folder to C:\inetpub\wwwroot.
- Rename the folder "osTicket".
- Reload IIS (Stop and start server).
- Go to: sites > default > osTicket; on the far right of the window, click on "Browse*:80".
- Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename "ost-sampleconfig.php" to "ost-config.php".
- Next, enable PHP extensions before continuing with osTicket.
- Go back to IIS and go to "sites > default > osTicket. Double click on PHP manager and then click on "Enable or disable an extension".
- Assign file permissions to everyone (Disable inheritance > Remove All, New Permissions > Everyone > All). Enable "php_imap.dll", "php_intl.dll" and "php_opcache.dll".
- Refresh the browser and osTicket's PHP extension changes will be shown.
  </p>
<br />

<p>
<img src="https://i.imgur.com/pdshWGR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Start filling out the form in os Ticket.
- Before completing the form, a database client is needed.
- Install HeidiSQL.
- Open HeidiSQL and create a new database using the name and password that was created for MySQL.
- Connect to session and create a database called "osTicket". Now that the database has been created, finish filling out the form. Use MySQL name and password on the form.
- Click install now.
</p>
<br />

<p>
<img src="https://i.imgur.com/X9x3jg8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
- Browse to the help desk login page: http://localhost/osTicket/scp/login.php.
- There's a little bit of cleanup necessary before proceeding
  - Delete: C:\inetpub\wwwroot\osTicket\setup.
  - Set permissions to “Read, Write and Execute" at : C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>

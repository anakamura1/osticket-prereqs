<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial walks through the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (Windows) / Windows App (MacOS)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>
<p>
Before we begin, please set up a Windows Virtual Machine in Azure. (www.github.com/anakamura1/vm-creation) </p>

<p>(4 vCPU's and 8Gib memory should be sufficient)</p>

<h2>Installation Steps</h2>

<table>
  <tr>
<td><img width="1114" alt="Screenshot 2025-01-08 at 8 04 06 PM" src="https://github.com/user-attachments/assets/b4c6e1df-267d-4fde-b536-653c858ebb86" /></td>
<td><img width="1117" alt="Screenshot 2025-01-08 at 8 04 29 PM" src="https://github.com/user-attachments/assets/a73f705b-d389-4908-b19b-71a2d6a214eb" /></td>
  </tr>
</table>

<p>
  Open to Control Panel -> Programs -> Program and Features -> Turn Windows features on or off
</p>
<br />

<table>
  <tr>
    <td><img width="413" alt="Screenshot 2025-01-08 at 8 05 02 PM" src="https://github.com/user-attachments/assets/9ddc0e56-bb4b-4a5f-b5dc-bb59d96c83f0" />
</td>
  </tr>
</table>
Expand IIS and click World Wide Web Services -> Application Development Features -> and check the CGI box
</p>
<br />

<table>
  <tr>
    <td>
<img width="460" alt="Screenshot 2025-01-08 at 8 06 06 PM" src="https://github.com/user-attachments/assets/537ea24b-fb2d-4fbd-93de-7fe425ee02dd" />
    </td>
  </tr>
</table>
<p>
  Open up Internet Explorer and type into the address bar "127.0.0.1" to load the IIS page.
</p>
<br />


<table>
  <tr>
<td><img width="650" alt="Screenshot 2025-01-08 at 8 09 47 PM" src="https://github.com/user-attachments/assets/3e9291cf-4600-4293-a160-37e78cd583f5" />
</td>
  </tr>
</table>
  Download the following [link](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract the files onto your desktop
  <p>From this file, install the PHP manager (PHPManagerForIIS_V1.5.0.msi) and install the Rewrite Module (rewrite_amd64_en-US.msi)</p>
<br />

<table>
  <tr>
    <td><img width="650" alt="Screenshot 2025-01-08 at 8 11 48 PM" src="https://github.com/user-attachments/assets/d4fbd401-96d5-4a5a-987b-626e8bf2165c" /></td>
  </tr>
</table>
<p>Create the directory C:\PHP. Go into the C drive and simply create a new folder titled "PHP". </p></p>
<br />

<table>
  <tr>
    <td>
      <img width="715" alt="Screenshot 2025-01-08 at 8 09 47 PM" src="https://github.com/user-attachments/assets/857b3c51-b096-4fc4-8528-ce8cecff1ae1" />
    </td>
<td><img width="715" alt="Screenshot 2025-01-08 at 8 09 47 PM" src="https://github.com/user-attachments/assets/78fc8eb9-102d-4719-a7bb-ad39380d3463" />
  </td>
  </tr>
</table>
<p>
From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder. 
</p>
<br />



<table>
  <tr>
<td><img width="415" alt="Screenshot 2025-01-08 at 8 23 40 PM" src="https://github.com/user-attachments/assets/edede72d-759b-46a2-a39e-415a9ff2eed5" />
</td>
  </tr>
</table>
<p>
Going back to the “osTicket-Installation-Files” folder, install VC_redist.x86.exe. and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
</p>
  <p>For the SQL setup follow these instructions below:  </p>
  <p>
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root
  </p>
<p>(BE SURE TO ENTER IN THE USERNAME AND PASSWORD CORRECTLY)
</p>
<br />

<table>
  <tr>
    <td><img width="413" alt="Screenshot 2025-01-08 at 8 05 02 PM" src="https://github.com/user-attachments/assets/9ddc0e56-bb4b-4a5f-b5dc-bb59d96c83f0" />
</td>
  </tr>
</table>
Expand IIS and click World Wide Web Services -> Application Development Features -> and check the CGI box
</p>
<br />

<table>
  <tr>
    <td>
<img width="700" alt="Screenshot 2025-01-08 at 8 25 47 PM" src="https://github.com/user-attachments/assets/9e26b0cb-0635-41d4-bb08-a39967209695" />
    </td>
    <td><img width="700" alt="Screenshot 2025-01-08 at 8 33 41 PM" src="https://github.com/user-attachments/assets/fcfb0652-ea13-4189-9b70-15f847687618" />
</td>
    <td><img width="700" alt="Screenshot 2025-01-08 at 8 35 02 PM" src="https://github.com/user-attachments/assets/b51ec393-4197-4f20-bdf2-8e7246827abe" />
</td>
  </tr>
</table>
<p>
  Next, open IIS and run it as administrator. Within IIS, open the PHP manager. Then select "Register new PHP version" and enter in "C:\PHP\php-cgi.exe"
</p>
<br />

<p><img width="500" alt="Screenshot 2025-01-08 at 8 36 31 PM" src="https://github.com/user-attachments/assets/0081bceb-2b23-4e94-8e0f-a2c3e11a479a" />
    </p>
<table>
  <tr>
    <td><img width="700" alt="Screenshot 2025-01-08 at 8 38 01 PM" src="https://github.com/user-attachments/assets/21397788-e226-49b3-bbf0-089a436f3c5f" /
</td>
    <td><img width="650" alt="Screenshot 2025-01-08 at 8 41 27 PM" src="https://github.com/user-attachments/assets/e2fac6c9-de6b-45fc-9b5e-a3aa1aabf7f8" />
</td>
  </tr>
</table>
<p>At this point, STOP and START the IIS. From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”. Once all is completed, STOP and START the IIS again.</p>

<table>
  <tr>
    <td><img width="700" alt="Screenshot 2025-01-08 at 8 44 24 PM" src="https://github.com/user-attachments/assets/a94fe929-737e-4ea3-924f-1f71c0ba4f60" />
</td>
    <td><img width="700" alt="Screenshot 2025-01-08 at 8 46 24 PM" src="https://github.com/user-attachments/assets/a7aa881b-152c-4c29-a26d-42122556a380" />
</td>
  </tr>
</table>

<p>In the IIS, Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
</p>


<p>
  A new site will appear on our browser. 
Go back to IIS, sites -> Default -> osTicket. Select osTicket and
double-click PHP Manager.
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
</p>
<p>
Now refresh the osTicket site in your browser.
</p>
<br>

<table>
  <tr>
    <td><img width="717" alt="Screenshot 2025-01-08 at 8 51 49 PM" src="https://github.com/user-attachments/assets/5bcc1437-2e00-42ba-b434-f72ff74d0fae" />
</td>
   <td> <img width="361" alt="Screenshot 2025-01-08 at 8 55 06 PM" src="https://github.com/user-attachments/assets/c4b2d4c2-57e7-4a96-b871-50f7d113818b" />
   </td>
    <td><img width="764" alt="Screenshot 2025-01-08 at 8 55 20 PM" src="https://github.com/user-attachments/assets/41319f9f-dfe7-4596-b879-c13408038197" />
</td>
    <td><img width="913" alt="Screenshot 2025-01-08 at 8 56 06 PM" src="https://github.com/user-attachments/assets/041b39d6-0ae4-420d-9f93-9e1be8aa6caa" />
</td>
  </tr>
</table>

<p>
 Now lets rename: ost-config.php
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<p>From ost-config.php, right click to access properties and select Advanced. We will Disable Inheritance and Remove all inherited permissions. Next, click Add -> Select a principal, enter "everyone" and select "Check names"</p>

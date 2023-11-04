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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Download files [HERE](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)


<h2>Installation Steps</h2>


- The first thing you are going to do is create a virtual machine by going to [Azure Portal](https://portal.azure.com/). Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

 - Once you have created your virtual machine you will want to conncet to it by using the public ip address the vm is setup with. You will connect using the remote desktop connection app. 
</p>
<br />

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/15e5f021-5a24-413b-9976-7a42fbf5da30"/>
</p>
<p>
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a4d0800d-5c91-4348-b2da-665a3ba1045a"/>
</p>
<p>
  
- Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select, Turn Windows features on and off.

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/07f93b59-1b7e-472e-a6d4-9897f753836e"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/be50256c-8ffe-4ac8-a8d5-d0ebe2e297c8"/>
</p>
<p>
  
 - You will want to install / enable IIS in Windows with CGI and Common HTTP Features
 - World Wide Web Services -> Application Development Features -> 
[X] CGI
[X] Common HTTP Features
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/b6cd3416-0869-49e5-a993-e7606e6295be"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/ef79d590-49a4-4f1a-ba41-f89b2a038bbc"/>
</p>
<p>
  
***NOTE*** Make sure all Common HTTP Features are checked.
 
 To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 
  It should look something like this. 
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a0d5d946-9e80-4671-9e49-a3ff6e1db261"/>
</p>
<p>
  
  
  
  
 - Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  Go through the install wizard and complete the install.
  
 - Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
  
 - Create a folder in the C drive called PHP.
  
 - From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/8c263b38-e7f8-407f-97f5-2c182dd44c25"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d1e5b1ff-5e6d-4d2b-af8d-1207991db39c"/>
</p>
<p>

 - Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
  
 - Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  Run the setup wizard:
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

  Make the new root password: Password1
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d0aedcb9-f57c-44c2-8b9b-20c001e3f34c"/>
</p>
<p>
  
  Execute the process on the next page.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/1420bf7c-1425-4e38-9664-f425205bef12"/>
</p>
<p>
  
 - Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator.
  The program should look like this.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/fa2bc7e1-9e7a-4a8b-9239-375b781de6ff"/>
</p>
<p>
  
 - We will now want to register PHP from within IIS.
  Click on PHP Manager
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/aba3571e-56a0-431d-893b-c60039d3d46f"/>
</p>
<p>
  
Register new PHP version.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d273b32e-b205-4c8d-9c85-9ed695210418"/>
</p>
<p>
  
You will want to provide a path to the php executable file (php-cgi.exe)). 
  Go to C Drive -> PHP -> click on php-cgi file.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d6643c4f-b1e1-4f50-b3a4-dff693e2c177"/>
</p>
<p>
  
  Restart the IIS server.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/52ec0e80-bba5-4c57-90c0-fd453a2a619d"/>
</p>
<p>
  
 - Install osTicket v1.15.8
  -Download osTicket from the Installation Files Folder
  -Extract and copy "upload" folder to c:\inetpub\wwwroot
  -Within c:\inetpub\root, Rename "upload" to "osTicket"
  
  Reload IIS again.
  
 - On IIS go to sites -> Default -> osTicket
  -On the right, click “Browse *:80”
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a3268538-337b-4c61-9f14-a38962a8f4f0"/>
</p>
<p>
  
  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/0eddd10b-c2e1-4d6d-9b50-d89b7c21477f"/>
</p>
<p>
  
  To enable the extensions:
  -Go back to IIS, sites -> Default -> osTicket
  -Double click PHP manager
  -Click "Enable or disable an extension"
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/81ac4b17-89d9-44fe-9663-4ae39c9f1f22"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/73a3b221-60f9-4ee1-9233-2623a9075680"/>
</p>
<p>
  
  We will want to enable three extensions from here.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/7ca1c063-27de-46eb-8761-6fabff7007a3"/>
</p>
<p>
  
  
 - Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder.
  Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
  We are going to rename the ost-sampleconfig.php to ost-config.php
  
  Now that we have renamed the files, right click on the file and go to properties.
  From there click security, click on advance, and disable the inheritance.
  We will select Remove all inherited permissions from this object.
  
  Now we will add new permissions.
  
  Click Add
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/e3f153dd-43b8-4859-8851-8aa73af581d8"/>
</p>
<p>
  
Select a principal
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/3fe9291a-a597-4057-982c-21e3ea652eed"/>
</p>
<p>
  
  
 Type "Everyone" in the box.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/33f72cbf-e9d4-4959-9f67-16a6605f08b8"/>
</p>
<p>
  
  Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/f55ae3a1-e8bc-4c56-adc9-b5f033cb7bc1"/>
</p>
<p>
  
  Click Apply and Ok.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/0577e54e-65be-4c1c-bf76-d99d6bac129d"/>
</p>
<p>
  
  Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page.
  Fill out the page as required except the Database Settings at the bottom of the page. We will get to that. 
  
  We will want to download and install HeidiSQL from the Installation Files. 
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/4fe31842-f36b-42b5-98b1-350b73fa466d"/>
</p>
<p>
  
  When the program is open we will create a new session in it.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/18da5c0b-a0cc-4207-8780-958f95d0ae44"/>
</p>
<p>
  
  We want to make sure the username is root and the password is Password1.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/42da86a1-37d1-4026-9824-a4bc31818b5b"/>
</p>
<p>
  
  Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.
  
  We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a200f0e0-2994-48de-a8b5-bb84725ad026"/>
</p>
<p>
  
  The last step is to do some clean up. We will want to delete the setup folder in our system. 
  -Delete: C:\inetpub\wwwroot\osTicket\setup
  Only delete the setup folder and nothing else.
  
  We then will want to set the permissions back to "Read" only in the ost-config.php file.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/e7796cec-114b-4c88-b828-7461f1a4d9b1"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/c769cd0d-a3a3-49fe-aeba-59d49733ab37"/>
</p>
<p>
  
  The last step after that is to login to osTicket on the browser.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/9c45c9dc-30c4-479c-bac3-1d6bca92ead4"/>
</p>
<p>
  
  Congrats! You have now successfully installed and setup osTicket!


  <h3 align = "right">Next Tutorial - <a href = "https://github.com/Cyber-singh/post-install-config">osTicket: Post-Installation Configuration</a></h3>


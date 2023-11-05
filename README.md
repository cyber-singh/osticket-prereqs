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
- osTicket 
- Download files [HERE](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<p>

<h2>Installation Steps</h2>
 
- To get started, the first thing you need to do is creat a virtual machine in the [Azure Portal](https://portal.azure.com/). Configure your virtual machine with Windows 10 Pro, specifically version 22H2. Remember, it's a good idea to set up the virtual machine with at least 2 vCPUs and 16 GBs of RAM.

 - After you've set up your virtual machine, the next step is to connect to it using the public IP address assigned to the VM. You can do this by using the Remote Desktop Connection application.

**NOTE: If you don't know how to create a virtual machine click [HERE](https://www.youtube.com/@cyber_singh)**

</p>

<br />

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/15e5f021-5a24-413b-9976-7a42fbf5da30"/>
</p>

<p> 
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a4d0800d-5c91-4348-b2da-665a3ba1045a"/>
</p>

****

<p>
 
- Once you've successfully connected to your virtual machine, the next step is to navigate to the Control Panel. Inside the Control Panel, locate the "Programs" section, and then choose "Turn Windows features on and off."

<br>

<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/07f93b59-1b7e-472e-a6d4-9897f753836e"/>


<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/be50256c-8ffe-4ac8-a8d5-d0ebe2e297c8"/>

</p>  
 
****

<p>
  
 - In the **"Turn Windows features on and off"** menu, make sure to install/enable **"IIS (Internet Information Services)"** with CGI and Common HTTP Features, to do so follow these steps:

1. Check the box for **"[X] IIS"** and expand it.
2. Inside **IIS**, expand **"World Wide Web Services"**.
3. Under **"Application Development Features"** check the box for **"[X] CGI"**.
4. Collapse the **"Application Development Features"** section.
5. Expand **"Common HTTP Features"**.
6. Make sure that every option under **"Common HTTP Features"** is checked.

</p>

<br>

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/b6cd3416-0869-49e5-a993-e7606e6295be"/>
</p>

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/ef79d590-49a4-4f1a-ba41-f89b2a038bbc"/>
</p>

 <p>
  
**NOTE: Make sure all **Common HTTP** Features are checked.**
  
</p>
<br>

 <p>
  
 - To verify that **IIS** is installed and enabled, open a web browser of your choice and enter **"127.0.0.1"** in the address bar. The resulting page should resemble the following..
  

<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a0d5d946-9e80-4671-9e49-a3ff6e1db261"/>

</p>

  ****
<p> 
 <h3>Now that IIS is enabled, here are the steps to follow:</h3>
</p>

 <br>
<p>
 
**Install PHP Manager for IIS:** From the [Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6), download [PHP Manager for IIS](https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=drive_link). Run the installation wizard and complete the installation.

</p>

<p>
 
 **Install the Rewrite Module:** From the [Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6), download [Rewrite Module](https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=drive_link). Run the installation to set up the Rewrite Module.
</p>

<p> 
 
**Create a PHP Folder:** Create a folder named **"PHP"** in the C drive **(C:\PHP)**.
</p>

<p>
 
**Download and Unzip PHP 7.3.8:** From the [Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6), download [PHP 7.3.8](https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=drive_link). Unzip the contents of the downloaded file into the **"C:\PHP"** directory.
</p>

<br>

<p>
 
**!! ATTENTION !!** If this appears, choose to “Keep” the file.
   
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/8c263b38-e7f8-407f-97f5-2c182dd44c25"/>
</p>

<p>
 <img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d1e5b1ff-5e6d-4d2b-af8d-1207991db39c"/>
</p>

****
<p>

 - Once you have downloaded and extracted the **zip File** into the **PHP Folder** on the **"C Drive"**, download and install the [VC_redist.x86](https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=drive_link) from the [Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6). 
  
 - Download and install [MySQL](https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=drive_link). Run the typical setup wizard and then after installation opt out for standard configuration.
<br>

 - Make the new root password: **Password1**
</p>

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d0aedcb9-f57c-44c2-8b9b-20c001e3f34c"/>
</p>

<br>

<p> 
 
 - Execute the process on the next page.
 
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/1420bf7c-1425-4e38-9664-f425205bef12"/>
</p>

****

<p>
 
 - Now that you've downloaded and installed the necessary files, search for "IIS" in the Windows search bar. Open IIS as an administrator, and the program should appear like this..
  
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/fa2bc7e1-9e7a-4a8b-9239-375b781de6ff"/>
</p>

****

<p>
 
 <h3>Now, to register PHP within IIS</h3>
 
  - Click on PHP Manager
  
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/aba3571e-56a0-431d-893b-c60039d3d46f"/>
</p>

<br>

<p>
 
 - Register new PHP version.
  
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d273b32e-b205-4c8d-9c85-9ed695210418"/>
</p>

<br>

<p>

 - To set up PHP, provide the path to the PHP executable file (php-cgi.exe). Navigate to the C Drive, then open the PHP folder and select the php-cgi file.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/d6643c4f-b1e1-4f50-b3a4-dff693e2c177"/>
</p>

<br>

<p>

  - Restart the IIS server.
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/52ec0e80-bba5-4c57-90c0-fd453a2a619d"/>
</p>

****

<p>
 
<h3>To install osTicket, follow these steps:</h3>

1. Download osTicket from the [Installation Files Folder](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

2. After downloading, extract the contents and locate the **"upload"** folder.

3. Copy the entire **"upload"** folder.

4. Navigate to the **"c:\inetpub\wwwroot"** directory.

5. Paste the **"upload"** folder in **"c:\inetpub\wwwroot"**.

6. Once pasted, within **"c:\inetpub\wwwroot"**, rename the **"upload"** folder to **"osTicket"**.

****

**To reload IIS and access your osTicket installation, follow these steps:**
  
1. Reload IIS by restarting the IIS service or performing an IIS reset.

2. In IIS, go to **"Sites"** and expand it.

3. Click to expand **"Default Web Site"**. 

4. Look for **osTicket**.

5. On the right side, click **"Browse** ***:80"**

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a3268538-337b-4c61-9f14-a38962a8f4f0"/>
</p>
<p>

<br>
  
 - Some extensions are not enabled on the **osTicket** browser.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/0eddd10b-c2e1-4d6d-9b50-d89b7c21477f"/>
</p>
<p>

<br>

**To enable PHP extensions for your osTicket installation, follow these steps:**

1. Return to IIS, go to **"Sites"**, and navigate to the **"Default Web Site"**.

2. Find the **"osTicket"** select it.

3. Locate and double-click on **"PHP Manager"**.

4. Inside the **"PHP Manager"**, click on **"Enable or disable an extension"**.

This will allow you to manage and enable the necessary **PHP extensions** for your **osTicket** application.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/81ac4b17-89d9-44fe-9663-4ae39c9f1f22"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/73a3b221-60f9-4ee1-9233-2623a9075680"/>
</p>
<p>

<br>
  
**In the PHP Manager, find and enable the following extensions:**

 - php_imap.dll
 - php_intl.dll
 - php_opcache.dll
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/7ca1c063-27de-46eb-8761-6fabff7007a3"/>
</p>
<p>

****  
  
 - After enabling the required extensions in IIS, the next step is to rename a file in your osTicket folder. Open the File Explorer and navigate to **"C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php"** Rename the file **"ost-sampleconfig.php"** to **"ost-config.php"**.
 
 - This file renaming step is essential for configuring osTicket correctly.


****  

After renaming the file to **"ost-config.php"**, follow these steps:

1. Right-click on the **"ost-config.php"** and go to **"Properties"**.

2. In the **"Properties"** window, select the **"Security"** tab.

3. Click on **"Advanced"**.

4. Within the Advanced Security Settings, you'll see an option to **"Disable inheritance"** Click on it.

5. Choose **"Remove all inherited permissions from this object"**.

By following these steps, you'll customize the security settings for the **"ost-config.php"** file.

****
  
<h3>Now we will add new permissions.</h3>

<br>

 - In the Advanced Security Settings for **"ost-config.php**", click on the **"Add"** button.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/e3f153dd-43b8-4859-8851-8aa73af581d8"/>
</p>

<br>

<p>
  
 - Next, you will need to select a principal (user or group) for which you want to set permissions.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/3fe9291a-a597-4057-982c-21e3ea652eed"/>
</p>

<br>

<p>  
  
 - Type **"Everyone"** in the box.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/33f72cbf-e9d4-4959-9f67-16a6605f08b8"/>
</p>

<br>

<p>

 - Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/f55ae3a1-e8bc-4c56-adc9-b5f033cb7bc1"/>
</p>

<br>

<p>
 
 - Click **"Apply"** and **"Ok"**.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/0577e54e-65be-4c1c-bf76-d99d6bac129d"/>
</p>

****

<p>
  
 - Once you have completed the file permissions setup, proceed to set up **osTicket** in your web browser. Click **"Continue"** on the osTicket web page.

 - Fill out the required information on the page, but leave the **"Database Settings"** section at the bottom of the page for now. We will address that shortly.

<br>
  
 - You will need to download and install **HeidiSQL** from the [Installation Files Folder](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6). This step is necessary for configuring the database settings for your osTicket installation.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/4fe31842-f36b-42b5-98b1-350b73fa466d"/>
</p>

<br>

<p>
  
 - Once **HeidiSQL** is open, you should proceed to create a new session within the application. 
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/18da5c0b-a0cc-4207-8780-958f95d0ae44"/>
</p>
<br>

<p>
  
 - Ensure that you set the username as **"root"** and the password as **"Password1"** during the configuration of the new session in **HeidiSQL**.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/42da86a1-37d1-4026-9824-a4bc31818b5b"/>
</p>
****

<p>
  
 - After successfully connecting to the session in HeidiSQL, return to the browser to complete the setup. In the "Database Settings" section of the browser, use "root" as the username and "Password1" as the password.

<br>
  
<h3>To create a new database in HeidiSQL and link it to osTicket, follow these steps:</h3>

1. In **HeidiSQL**, right-click on the section on the left where it says **"Unnamed"**.

2. Select **"Create New"** and then choose **"Database"**

3. Name the new database **"osTicket"**.

 - Once you've set up the new **"osTicket"** database in **HeidiSQL**, return to the osTicket browser and, under **"MySQL Database"**, type in **"osTicket"**. This will connect your osTicket installation to the newly created database.

<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/a200f0e0-2994-48de-a8b5-bb84725ad026"/>
</p>
****

<p>

 - As the final step, delete the **"setup"** folder from your system. Navigate to **"C:\inetpub\wwwroot\osTicket"** and delete the **"setup"** folder. Ensure that you only delete the **"setup"** folder and nothing else. This cleanup step is important to secure your **osTicket** installation.

<br>
  
 - After deleting the **"setup"** folder, you should set the permissions for the **"ost-config.php"** file back to **"Read-only"** This helps maintain the security of your **osTicket** installation.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/e7796cec-114b-4c88-b828-7461f1a4d9b1"/>
</p>
<p>
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/c769cd0d-a3a3-49fe-aeba-59d49733ab37"/>
</p>

****

<p>
  
 - After completing the setup and making the necessary changes, the final step is to log in to **osTicket** through your web browser. You can now access and use **osTicket** to manage your support tickets and customer inquiries.
  
<p>
<img src="https://github.com/cyber-singh/osticket-prereqs/assets/149118027/9c45c9dc-30c4-479c-bac3-1d6bca92ead4"/>
</p>
<p>
  
<h3>Congratulations! You have successfully completed the installation and setup of osTicket</h3>.


  <h3 align = "right">Next Tutorial - <a href = "https://github.com/Cyber-singh/post-install-config">osTicket: Post-Installation Configuration</a></h3>


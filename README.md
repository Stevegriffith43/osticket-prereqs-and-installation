<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Creation of the Virtual Machine
- RDC (Remote desktop connection) into the VM created
- Install/Enable IIS in Windows with CGI and common HTTP Features
- Installation of OsTicket

<h2> Creation of the Virtual Machine under Microsoft Azure </h2>


- Establishing the Virtual Machine within the Microsoft Azure framework tailored to our environment
- This involves the straightforward task of crafting a machine with fundamental configurations, including specifications such as size, operating system, and network settings, all meticulously designed to suit the 
  requirements of our lab environment.

<h3>Create an Azure Virtual Machine Windows 10, 4 vCPUs</h3>

- Name: Vm-osticket
- Username: labuser (for example/whatever you chose)
- Password: osTicketPassword1! (for example/whatever you chose)

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/ae62dbd4-9536-4686-ad03-2c4e186d1ce6)   
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/dcc855c6-d4dd-47fa-87d7-0fca4cb55fca)

<h2> Establishing a remote desktop connection to the virtual machine that was set up in the previous step </h2>

- Launch the Remote Desktop Connection application on your local machine. This application may be referred to as "Remote Desktop" or "Remote Desktop Connection," depending on your operating system.
- In the Remote Desktop Connection window, input the (public) IP address of the virtual machine that was set up in Part 1 and connect.
- When prompted, enter the username and password for the virtual machine. These credentials should have been set up during the creation of the virtual machine.
- If a security certificate warning appears, review the information and, if you trust the connection, accept or install the certificate to proceed.

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/1f38b591-e45f-41f3-baba-95427474ac13)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/e3ffa6fd-d236-46d3-8638-57a43e1e7c35)

<h2> Install and Enable IIS in Windows with CGI and common HTTP Features(Link to installation files below for the following steps</h2>

<div>
  <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Installation files</a>
</div>

<h3>Install IIS (Internet Information Services)</h3>

- [X] World Wide Web Services 
- [X] Application Development Features 
- [X] CGI
- [X] Common HTTP Features

<h3>Configuring IIS Console</h3>

- [X] Internet Information Services 
- [X] Web Management Tools 
- [X] IIS Management Console
- We want to check and make sure the console is installed by going to (127.0.0.1) IIS browser.  

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/b42e80b5-544d-4b8e-b1d6-96850a0b3664)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/6faac562-744d-4ba5-ab1b-9d3aab2b854e)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/04398a2c-09f1-4e04-a4bd-56eb6340fdaf)
![image](https://github.com/user-attachments/assets/d6a7d9f7-5857-4132-804f-f07f678fa205)


<h3>Install PHP</h3>

- Download PHP: Go to the official PHP website and download the appropriate PHP version for your server.
- Install PHP: Follow the installation instructions, making sure to configure PHP to work with IIS.

 ![image](https://github.com/user-attachments/assets/cf4febb2-d828-49cb-b7f1-826e285a3829)

<h3>Integrate the Rewrite Module</h3>

- Download URL Rewrite Module: Download the URL Rewrite Module from the Microsoft website.
- Install Rewrite Module: Run the installer and follow the instructions to integrate the rewrite module with IIS.
- Create the directory C:\PHP (Windows>New Folder>Name it PHP)
- From the Installation Files < download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

![image](https://github.com/user-attachments/assets/598c9caa-7e7e-4e55-92cb-5233337a044d)
![image](https://github.com/user-attachments/assets/6654d0fa-f0a8-4ffc-900c-ed0b5028a4cc)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/f86a9ec6-a5bc-4f96-9f45-566fd31b7fd1)
![image](https://github.com/user-attachments/assets/2268b9ae-7c44-4bc7-9fde-c03a9fd982f6)
![image](https://github.com/user-attachments/assets/937498c7-f90c-4492-92a1-091d8255d28e)

<h3>Install VC (Visual C++ Redistributable)</h3>

- Download VC Redistributable: Go to the Microsoft website and download the required Visual C++ Redistributable packages.
- Install VC Redistributable: Run the installers for the downloaded packages to install the necessary runtime libraries.

![image](https://github.com/user-attachments/assets/29acecc1-1ce4-4c8a-9434-df75a922d7e8)

<h3>Install MySQL</h3>

- Typical Setup 
- Launch Configuration Wizard (after installation) 
- Standard Configuration 
- username: root
- pass: Password1

![image](https://github.com/user-attachments/assets/75bcfa78-eda1-4b27-acb1-fe0566844d9e)
![image](https://github.com/user-attachments/assets/2b551cc5-d257-4cc0-a514-da32fbb11863)

<h3>Verify Component Installation</h3>

- Open IIS as Admin
- Register PHP from within IIS
- Reload IIS (Open IIS, Stop and Start the server) (Repeat when adding new features to IIS)

![image](https://github.com/user-attachments/assets/8aad48a4-392f-4483-9ff4-92932f3f67a7)
![image](https://github.com/user-attachments/assets/52caf9f7-d35c-4522-9d3e-e4842263dce0)
![image](https://github.com/user-attachments/assets/62674d83-28eb-4adf-bee4-951e4ea93b38)
![image](https://github.com/user-attachments/assets/b8e1ceaf-49f7-46b6-86a6-b87823b3a8b3)

<h3>Install osTicket v1.15.8</h3>

- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot (Our web servers main folder)
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Make sure to restart IIS to confirm changes
- Go to sites -> Default -> osTicket
- On the right, click “Browse *:80”

![image](https://github.com/user-attachments/assets/37d0ee92-8560-49b4-bcc4-c1d1b8a7ce8d)
![image](https://github.com/user-attachments/assets/1bc87f16-90d6-4ad5-b041-a3e72b638ef0)
![image](https://github.com/user-attachments/assets/684ac26f-b015-4148-b92a-425975aa2b52)
![image](https://github.com/user-attachments/assets/4f6c588c-e9ea-4db6-b648-cb2c1a1dbf05)
![image](https://github.com/user-attachments/assets/5dbc83cc-3d8f-4a13-8282-7536b38c40a8)

<h3>Enabling some extensions</h3>

- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
  -(Enable: php_imap.dll)
  -(Enable: php_intl.dll)
  -(Enable: php_opcache.dll)
- Refresh the osTicket site in your browse, observe the changes

![image](https://github.com/user-attachments/assets/1c2ad104-6b67-4580-bf4a-a2e70d08a3ca)
![image](https://github.com/user-attachments/assets/448b2fa4-30fb-4ca3-b749-8b7cff2e5019)
![image](https://github.com/user-attachments/assets/288dad0c-0e0e-4660-a920-ba984472e10b)

<h3>Rename: ost-config.php</h3>

- From: C:\inetpub\wwwroot\osTicket\include\(ost-sampleconfig.php)
- To: C:\inetpub\wwwroot\osTicket\include\(ost-config.php)

![image](https://github.com/user-attachments/assets/98194549-5127-4fc4-8f29-6a2fa9a1b791)

<h3>Assign Permissions: ost-config.php</h3>

- Right-click on the file and go to properties > Security > Advanced
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All
- Essentially giving everyone full control

![image](https://github.com/user-attachments/assets/f33134b8-7e07-423a-afa6-58de51b43791)
![image](https://github.com/user-attachments/assets/f45cdfeb-8aea-4483-87ac-b1f95c82d14f)
![image](https://github.com/user-attachments/assets/ced3ffa1-daa6-43c4-8461-4d0af91af0da)
![image](https://github.com/user-attachments/assets/f5492650-d2fa-42d3-8b84-d374dcf31eaf)
![image](https://github.com/user-attachments/assets/4438002e-6767-45ef-85b1-04445b433ca8)
![image](https://github.com/user-attachments/assets/4e791052-2d6a-4567-83c8-bcb506acb678)

<h3>Continue Setting up osTicket in the browser (click Continue)</h3>

- Name Helpdesk (John Help Desk)
- Default email (John@helper.com)
- Fill in name and email (John Doe)
- username: John pass: Password1
  
![image](https://github.com/user-attachments/assets/e1bd0748-1381-4cbf-930d-119973dedf83)

<h3>From the Installation Files, download and install HeidiSQL.</h3>

- Open Heidi SQL (Allows us to connect to the SQL database)
- Create a new session, root/Password1
- Connect to the session
- Create a database called “osTicket”

![image](https://github.com/user-attachments/assets/8c895a09-5224-4555-a20c-73f1defd7680)
![image](https://github.com/user-attachments/assets/3cab98c7-0dfe-46ea-9be0-6b1909092f83)
![image](https://github.com/user-attachments/assets/3f8aac90-79e0-425b-a428-8bc70737c4c8)
![image](https://github.com/user-attachments/assets/38abbb0d-eeb2-4e7f-8039-8d91b49f1c8c)

<h3>Continue Setting up osticket in the browser</h3>

- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: Password1
- Click “Install Now!”

![image](https://github.com/user-attachments/assets/ff6f244e-4a1b-4f3c-bdcd-820fda1a1041)

<h3>Clean up steps</h3>

- Delete: C:\inetpub\wwwroot\osTicket\setup
- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php (Again, you will right click to properties > Security > Advanced)

![image](https://github.com/user-attachments/assets/a6768067-742c-4b8d-8c15-aee3b8b70534)
![image](https://github.com/user-attachments/assets/5714db9a-cf55-4017-954c-44cafaab7a41)

<h3>Congratulations!</h3>

![image](https://github.com/user-attachments/assets/976ad6a5-02f9-4358-942a-1d2f9e486f69)

 - Browse to your help desk login page: http://localhost/osTicket/scp/login.php (Admin)
 - End Users osTicket URL: http://localhost/osTicket/ (End Users)
 - Try logging into the admin account to check and make sure it works.




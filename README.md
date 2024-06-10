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

- Creation of the Virtual Machine
- RDC into the VM created
- Install/Enable IIS in Windows with CGI and common HTTP Features


<h2>Part 1: Creation of the Virtual Machine under Microsocft Azure </h2>

<p>
In the initial phase, Part 1 entails establishing the Virtual Machine within the Microsoft Azure framework, tailored specifically for our environment. This involves the straightforward task of crafting a machine with fundamental configurations, including specifications such as size, operating system, and network settings, all meticulously designed to suit the requirements of our lab environment.
</p>
<br />

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/ae62dbd4-9536-4686-ad03-2c4e186d1ce6)   
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/dcc855c6-d4dd-47fa-87d7-0fca4cb55fca)


<p>
Moving on to Part 2, it will involve establishing a remote desktop connection to the virtual machine that was set up in Part 1. This step facilitates seamless access to the virtual environment created earlier, enabling efficient management and utilization of resources as per our project's needs.
</p>
<br />

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/1f38b591-e45f-41f3-baba-95427474ac13)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/e3ffa6fd-d236-46d3-8638-57a43e1e7c35)

<p>
Continuing with Part 3, the focus shifts to installing the prerequisites essential for deploying the osTicket system. This entails configuring crucial components like IIS (Internet Information Services), including CGI and Common HTTP Features. Additionally, it involves setting up the ISS management console, web management tools, installing PHP, integrating the rewrite module, VC, and MySQL, all pivotal for a smooth installation and operation of the osTicket system within our environment.
</p>
<br />

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/b42e80b5-544d-4b8e-b1d6-96850a0b3664)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/6faac562-744d-4ba5-ab1b-9d3aab2b854e)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/04398a2c-09f1-4e04-a4bd-56eb6340fdaf)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/a8423e35-406f-4c3b-8ea8-48e21e499be3)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/89bdc30e-6007-47f4-99f9-6f3aeee0884c)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/f86a9ec6-a5bc-4f96-9f45-566fd31b7fd1)

<p>
To kick off the process, begin by accessing IIS as an administrator. Once within IIS, proceed to register PHP. Following this, reload IIS by stopping and then restarting the server. Moving on to the installation of osTicket v1.15.8, begin by downloading the osTicket package from the designated Installation Files Folder. Extract the contents and transfer the "upload" folder to the directory "c:\inetpub\wwwroot". Within this directory, rename the "upload" folder to "osTicket". Reload IIS once again by stopping and then starting the server. Navigate to sites -> Default -> osTicket, and on the right, initiate browsing by clicking "Browse *:80".
</p>
<br />

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/d5a6f9fc-20ea-4a20-987f-20150bf59dc8)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/ef6b9468-e6f8-41c8-85cf-ec4b8b014c91)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/33e210f8-0b5a-4283-923f-64e3b8a73dc3)

<p>
Following the initial setup, it's crucial to note that certain extensions may not be enabled by default. To address this, return to IIS and navigate to sites -> Default -> osTicket. Double-click on PHP Manager, then select "Enable or disable an extension". Proceed to enable the extensions: php_imap.dll, php_intl.dll, and php_opcache.dll. After enabling these extensions, refresh the osTicket site in your browser to observe the changes.

Next, rename the file "ost-config.php" from its original location at C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.

Following this, it's essential to assign permissions to "ost-config.php". Disable inheritance and remove all existing permissions, then grant new permissions to Everyone with full access.

Once these steps are completed, continue setting up osTicket in your browser by clicking "Continue". Here, provide the necessary details such as naming the helpdesk and specifying the default email address to receive communication from customers.

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/c9c666ae-181f-48db-b69c-fe50e88dacf0)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/3fca7acb-e796-4759-b2d4-1579eae8869b)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/e096dc7b-6ad7-4834-914c-2686905de879)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/eb25c3af-41e2-4f25-8c45-7f7c852210d6)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/5f14b6e4-8dfa-45d6-be88-609ecae15723)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/5fd707e4-b468-4d5e-b941-7cd02f807144)

</p>
<br />

<p>
  
After assigning permissions to "ost-config.php" by disabling inheritance and granting full access to Everyone, proceed with the osTicket setup in your browser by clicking "Continue". Here, name your helpdesk and specify the default email address to receive communication from customers.

Subsequently, download and install HeidiSQL from the Installation Files. Open HeidiSQL and create a new session using the credentials root/Password1. Connect to the session and then create a new database named "osTicket".

Return to the osTicket setup in your browser and provide the following details:
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: Password1
Click "Install Now!" to proceed with the installation.

Upon successful installation, congratulations! Hopefully, there are no errors encountered. You can now browse to your help desk login page to begin utilizing osTicket.
</p>
<br />

![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/d51be9c0-4587-45ac-a3d0-3c72ad2d3522)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/82939832-1959-4380-b5da-11466610d81e)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/59161e7c-a53c-4560-8de0-963e7a33fd48)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/9fd9abfe-a1f9-4887-b934-cf35414a6f0d)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/4e0705ce-98eb-4f14-96c0-8e13bd71a1b4)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/f68fea9d-0bde-4c90-874d-4cbe6b72dcfd)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/985c3fc0-96c3-4f6f-8888-4438c85b1f70)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/6b8af032-b6d5-4ca3-9f10-73b5a058bf8a)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/02c72fe8-71b1-4797-a9f4-74602c3c77b7)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/3ca257cd-3779-4a16-bc44-b3faf166a808)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/694f528c-762f-40a5-a8f3-27c89c67612b)
![image](https://github.com/Stevegriffith43/osticket-prereqs/assets/118018853/d1cb2a2d-2c81-403a-a826-80f55f59da5e)











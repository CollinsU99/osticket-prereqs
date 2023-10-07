<p align="center">
<img src="https://i.imgur.com/SIOPg5j.png" alt="1"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

This tutorial provides a step-by-step guide to installing osTicket, an open-source help desk ticketing system. It includes information on the prerequisites for installation and the installation process itself.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute) 
- Remote Desktop (RDP)
- OsTicket 

<h2>Operating Systems Used </h2>

- Windows 10 Pro (22H2)

<h2>osTicket Installation Files</h2>

https://drive.google.com/drive/folders/1mKAD1ZaP1e3F0FInXuAlQ3Pcucz4Mb3O?usp=sharing

<h2>List of Prerequisites</h2>

 - Create a Resource Group
 - Create an Azure Virtual Machine
 - Install and enable IIS (Internet Information Services)
 - HeidiSQL
 - MySQL
 - OsTicket
 - PHP Manager
 - php
 - Rewrite
 - VC_redist

<h2>Installation Steps</h2>

<p align="center">
<img src="https://i.imgur.com/jJAiw1z.png" height="80%" width="80%" alt="img"/>
</p>

Go to your Azure portal https://portal.azure.com/ and login. In your Azure home page, click the search bar and search for "resource group". Click "Resource groups".

<p align="center">
<img src="https://i.imgur.com/q30fcm3.png" height="80%" width="80%" alt="img"/>
</p>

Click "Create" tab at the top left.

<p align="center">
<img src="https://i.imgur.com/G0iY3xD.png" height="80%" width="80%" alt="img"/>
</p>

Select your Azure subscription, we will name the resource group "RG-osTicket". Select "(US) West US 3" for the Region, and click "Review + create" tab at the bottom left. 

<p align="center">
<img src="https://i.imgur.com/kaWmyCc.png" height="80%" width="80%" alt="img"/>
</p>

Click the notification tab at the top right and confirm that the resource group "RG-osTick" has been created.

<p align="center">
<img src="https://i.imgur.com/yOJUCM3.png" height="80%" width="80%" alt="img"/>
</p>

Click the search bar and search for "virtual machine". Click "Virtual machines".

<p align="center">
<img src="https://i.imgur.com/FFhfzEL.png" height="80%" width="80%" alt="img"/>
</p>

Click the "Create" tab at the top left and select "Azure virtual machine".

<p align="center">
<img src="https://i.imgur.com/rKd4Hxw.png" height="80%" width="80%" alt="img"/>
</p>

Select your Azure subsription, select the resource group we created earlier "RG-osTicket", name the virtual machine "vm-osticket", select (US) West US 3 for the region, select "No infrastructure redundancy required" for the availability options, select "Standard" for Security type, select "Windows 10 Pro, version 22H2 - x64 Gen2 (free eligible services)" for Image, leave VM architecture as defualt, select "Standard_D4s_v3 - 4 vcpus, 16 GiB memory" for the Size. We will use "labuser" as the username, and make sure you use a unique password.

NOTE: Write down your username and password, we will need it later.

Leave "Public inbound ports" and select inbound ports" as default. Check the licensing box and click the Networking tab at the top.

<p align="center">
<img src="https://i.imgur.com/aUVAOqk.png" height="80%" width="80%" alt="img"/>
</p>

The Virtual network (NIC), Subnet, and Public IP will automatically be created for us, so make sure they all say (new). Leave every thing as default, and click "Review + create" tab at the bottom left. 

<p align="center">
<img src="https://i.imgur.com/IWBDQZj.png" height="80%" width="80%" alt="img"/>
</p>

The "Validation pass" message indicates that all of the required information has been provided and that the VM can be created. Go ahead an click the "Create" tab at the bottom left.

<p align="center">
<img src="https://i.imgur.com/RNQ208q.png" height="80%" width="80%" alt="img"/>
</p>

The "Validation is in progress" message indicates that the Virtual machine is being created and configured. This process can take several minutes.

<p align="center">
<img src="https://i.imgur.com/BZxxbil.png" height="80%" width="80%" alt="img"/>
</p>

The message "Your deployment is complete" means that the Azure virtual machine (VM) has been successfully created and configured.

<p align="center">
<img src="https://i.imgur.com/oV6Qwyj.png" height="80%" width="80%" alt="img"/>
</p>

Click the search bar, and click "Virtual machines".

<p align="center">
<img src="https://i.imgur.com/O8O0QBq.png" height="80%" width="80%" alt="img"/>
</p>

Click the virtual machine we just created.

<p align="center">
<img src="https://i.imgur.com/wGfGhSB.png" height="80%" width="80%" alt="img"/>
</p>

Copy the Public IP address.

<p align="center">
<img src="https://i.imgur.com/gChFsZc.png" height="80%" width="80%" alt="img"/>
</p>

On your local computer search box, search for "remote desktop", and click "Open"

<p align="center">
<img src="https://i.imgur.com/dDYXiBF.png" height="80%" width="80%" alt="img"/>
</p>

Paste your VMs Public IP address you copied and click the "Connect" button.

<p align="center">
<img src="https://i.imgur.com/neUPf5p.png" height="80%" width="80%" alt="img"/>
</p>

Click "More choices" > "Use a different account", go ahead and login with the username and password you used when you created your virtual machine, and click "Ok". 

<p align="center">
<img src="https://i.imgur.com/2ZPAvQj.png" height="80%" width="80%" alt="img"/>
</p>

We've now loged into our virtual machine. Select "No" for the options and click the "Accept" button.

<p align="center">
<img src="https://i.imgur.com/eRw8ia9.png" height="80%" width="80%" alt="img"/>
</p>

Select the "Yes" button.

Copy this link https://drive.google.com/drive/folders/1mKAD1ZaP1e3F0FInXuAlQ3Pcucz4Mb3O?usp=sharing 

This link contains all the installation files we will need. We will open it up inside the virtual machine because it's much easier to deal with there.

<p align="center">
<img src="https://i.imgur.com/R9bRAnY.png" height="80%" width="80%" alt="img"/>
</p>

In your virtual machine, double-click the "Microsoft Edge" application to open it.

<p align="center">
<img src="https://i.imgur.com/ARKjwcV.png" height="80%" width="80%" alt="img"/>
</p>

Click "Search without your data" > "Don't allow" > "Confirm and continue" > "Continue without this data" > "Confirm and start browsing". 

<p align="center">
<img src="https://i.imgur.com/rk6m5EW.png" height="80%" width="80%" alt="img"/>
</p>

Paste the link you copied in the search bar and press the Enter key.

We will now install and enable IIS

<p align="center">
<img src="https://i.imgur.com/xvSMNcH.png" height="80%" width="80%" alt="img"/>
</p>

NOTE: Internet Information Services (IIS) is a web server that osTicket runs on. IIS is created by Microsoft that and can be used to host a wide variety of websites and web applications.

Right-click the Start Menu and click "Run".

<p align="center">
<img src="https://i.imgur.com/jXSncgO.png" height="80%" width="80%" alt="img"/>
</p>

Type "control" and click the "Ok" button.

<p align="center">
<img src="https://i.imgur.com/PArDvYE.png" height="80%" width="80%" alt="img"/>
</p>

Click "Programs".

<p align="center">
<img src="https://i.imgur.com/x2YcYev.png" height="80%" width="80%" alt="img"/>
</p>

Click "Turn Windows features on or off".

<p align="center">
<img src="https://i.imgur.com/yxo745J.png" height="80%" width="80%" alt="img"/>
</p>

Scroll to "Internet Information Services" and check the box; click the plus (+) to expand it. Expand "World Wide Web Services", expand "Application Development Features", go ahead and check "CGI".

<p align="center">
<img src="https://i.imgur.com/UuVvmoH.png" height="80%" width="80%" alt="img"/>
</p>

Collaps "Application Development Features" and expand "Common HTTP Features". Make sure all the boxes are checked, and click the "Ok" button. 

<p align="center">
<img src="https://i.imgur.com/LZ7RzhM.png" height="80%" width="80%" alt="img"/>
</p>

The image above shows that the IIS web services are being installed.

<p align="center">
<img src="https://i.imgur.com/Qx022SW.png" height="80%" width="80%" alt="img"/>
</p>

IIS is now installed, click the "Close" button.

<p align="center">
<img src="https://i.imgur.com/Qx022SW.png" height="80%" width="80%" alt="img"/>
</p>

Let's confirm that IIS is installed on our VM. Open Microsoft Edge and search for "127.0.0.1"
















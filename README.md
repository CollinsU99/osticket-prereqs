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

- Windows 10 (21H2)

<h2>osTicket Installation Files</h2>

https://drive.google.com/drive/folders/1mKAD1ZaP1e3F0FInXuAlQ3Pcucz4Mb3O?usp=sharing

<h2>List of Prerequisites</h2>

 - Create a Resource Group
 - Create an Azure Virtual Machine
 - Enable IIS
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
<img src="https://i.imgur.com/BZxxbil.png" height="80%" width="80%" alt="img"/>
</p>































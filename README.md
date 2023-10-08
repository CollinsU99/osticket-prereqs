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
 - Downlaod and install "PHPManagerForIIS_V1.5.0.msi"
 - Download and install "rewrite_amd64_en-US.msi"
 - Create the "C\PHP" directory
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

Click the "Create" tab at the top left.

<p align="center">
<img src="https://i.imgur.com/G0iY3xD.png" height="80%" width="80%" alt="img"/>
</p>

Select your Azure subscription, we will name the resource group "RG-osTicket". Select "(US) West US 3" for the Region, and click the "Review + create" tab at the bottom left. 

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

Paste the link you copied in the search bar and press the Enter key. We will come back to this page later.

We will now install and enable IIS

<p align="center">
<img src="https://i.imgur.com/xvSMNcH.png" height="80%" width="80%" alt="img"/>
</p>

NOTE: Internet Information Services (IIS) is a web server that osTicket runs on. Microsoft created IIS, and it can be used to host a wide variety of websites and web applications.

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
<img src="https://i.imgur.com/7Ijcz0x.png" height="80%" width="80%" alt="img"/>
</p>

To confirm if IIS was actually installed on our VM, open Microsoft Edge, search for "127.0.0.1" on the search bar, and click Enter.

NOTE: "127.0.0.1" is the loopback address, which is a special IP address that maps to the local computer. It's essentially saying, "Try to load a webpage that's running off myself". So, it loaded the default IIS website, which confirms that the webservices are working.

If it loads a page like the one in the image above, it means the installation was successful.

<p align="center">
<img src="https://i.imgur.com/EppfODe.png" height="80%" width="80%" alt="img"/>
</p>

Next, we will download and install "PHPManagerForIIS_V1.5.0.msi".

Go back to the osTicket installation files web page, and click "PHPManagerForIIS_V1.5.0.msi".

<p align="center">
<img src="https://i.imgur.com/mgAXtVg.png" height="80%" width="80%" alt="img"/>
</p>

Click "Download".

<p align="center">
<img src="https://i.imgur.com/pCPkNq1.png" height="80%" width="80%" alt="img"/>
</p>

Disregard the warning and click "Download Anyway".

<p align="center">
<img src="https://i.imgur.com/cWtF26W.png" height="80%" width="80%" alt="img"/>
</p>

After it's downloaded, double-click "File Explore" in the taskbar.

<p align="center">
<img src="https://i.imgur.com/7b7NSYM.png" height="80%" width="80%" alt="img"/>
</p>

Click "Downloads" and double-click "PHPManagerForIIS_V1.5.0". PHPManagerForIIS_V1.5.0 installation window will pop up. Click "Next", select "I Agree" and click "Next" > "Close".

Close File Explorer.

<p align="center">
<img src="https://i.imgur.com/YLRxOsU.png" height="80%" width="80%" alt="img"/>
</p>

If you can't download any of the files, click the down arrow in the search bar, select "continue allowing automatic downloads of multiple files", and click "Done".

Go back to the osTicket installation files web page and download "rewrite_amd64_en-US.msi" just as we did for "PHPManagerForIIS_V1.5.0".

NOTE: The "rewrite_amd64_en-US.msi" allows osTicket to use URL rewriting. URL rewriting is a technique that allows us to change the way that URLs are displayed to users.

<p align="center">
<img src="https://i.imgur.com/GXvIgT5.png" height="80%" width="80%" alt="img"/>
</p>

After it's downloaded, click "File Explore" in the taskbar. Double-click "rewrite_amd64_en-US", check the license agreement box, and click "Next" > "Install" > "Finish".

<p align="center">
<img src="https://i.imgur.com/CwWRA0w.png" height="80%" width="80%" alt="img"/>
</p>

Let's create the "C\PHP" directory.

Open File Explorer, click "This PC" and double-click "Windows C:". 

<p align="center">
<img src="https://i.imgur.com/JbiNrb7.png" height="80%" width="80%" alt="img"/>
</p>

In "Windows C:", right-click on an empty space, click "New", click "Folder".

<p align="center">
<img src="https://i.imgur.com/glMjIz4.png" height="80%" width="80%" alt="img"/>
</p>

Create a folder called "PHP"

<p align="center">
<img src="https://i.imgur.com/x53XakV.png" height="80%" width="80%" alt="img"/>
</p>

Next let's download "php-7.3.8-nts-Win32-VC15-x86.zip".

Dowload it just as we did for previous files.

<p align="center">
<img src="https://i.imgur.com/x53XakV.png" height="80%" width="80%" alt="img"/>
</p>

Go back to File Explorer, and right-click "php-7.3.8-nts-Win32-VC15-x86.zip"







<h1>Installing/ Setting up Active Directory on Windows Server on Virtual Machine</h1>
This is a tutorial for setting up a basic Active Directory and VM at home so you can practice any skills you want.

<h2>Environments and Technologies Used</h2>

- VMware Workstation Pro (17.5.2)
- Remote Desktop
- Windows Server 2022 ISO (64-bit)

<h2>Operating Systems Used- </h2>

- Windows 10</b> (21H2)

<h2>Basic Steps covered in Tutorial-</h2>

- Download/Setup of VMware Workstation Pro and Windows Server 2022.
- Account Creation of VMware Workstation Pro.
- Download Active Directory Tools and apply features in VM.
- Create an Active Directory (AD) domain and promote the server to a Domain Controller.
- Create Organizational Units (OUs) for different fictional departments.
- Create Accounts within OU's.
<h3 align="center"> Helpful Links</h3> 
-https://knowledge.broadcom.com/external/article?articleNumber=368667 ( VMware Workstation Pro) <br />
-https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022 (Windows Server 2022)

<h2>Downloading Technology/ Environments</h2>
<br / >
<p>
  Click the first link in "Helpful Links" and create a Broadcom account to access VMware Workstation's Free Download:
</p>
  <img src="https://github.com/user-attachments/assets/bc7ea7fb-c148-4cd1-a47c-8cbd3ecdedf5: height="75%" width="100%" alt="Download VMware Workstation"/>
  <br />
<h3 align="center"> Downloading VMware Workstation Pro</h3>
<p>
Download Version 17.5.2
  <img src="https://i.imgur.com/ewueu9b.png: height="75%" width="100%" alt="O"/>
</p>
<p>
  When you double-click the download pop-up and follow the instructions the setup wizard displays, make sure to select "Personal Use" at the end. 
  <img src="">
</p>
<br />
<br />
<h3 align="center">Downloading Windows Server 2022</h3>
<br />
<p>
  Click the second link under "Helpful Links" to be sent to the download website.
</p>
<p>
  <img src="https://i.imgur.com/i3sa7FH.jpg" height="75%" width="100%" alt="Support agent login"/>
</p>
<br />
<br />
<h2>Virtual Machine Boot Up</h2>
<br />
<p>
  The focus for the next portion will be booting up our Virtual Machine and Configuring the Windows Server on VMware Workstation Pro
</p>
<h3 align="center">Creating a New Virtual Machine</h3>
<br />
<p>
When you load VMware Workstation Pro, you will view a screen with three selections. Pick the left-most that says "Create a New Virtual Machine"
  <img src="">
</p>
<p>
The Virtual Machine Wizard will show, click next and select "I will install the operating system later" then hit next. We will use the Windows Server 2022 download for this section later. 
  <img src="">
</p>
<p>
Select the guest OS as Microsoft Windows, then click the "Version" tab and select "Windows Server 2022", then hit next. 
  <img src="https://i.imgur.com/wVucqKf.png" height="75%" width="100%" alt="Communication"/>
</p>
<p>
For the next section, you may name your VM however you see fit, then select next.
</p>
<p> 
For Specific Disk Capacity, change the Maximum disk size to "20GB" and select next to officially create your Virtual Instance!
  <img src="">
</p>
<p>
Once you view a blank screen, which is your powered-off VM, right-click whatever you named your VM on the left tab and go to CD/DVD (SATA). Then, click the "use ISO image file" to select your Windows Server 2022 file. 
  <img src=""> 
</p>
<p>
  Then, select "Ok" to load in your ISO and power on your Virtual Machine! (Important: When you view the message "Press any key to boot from CD or DVD" click any button to avoid issues with the bootup. If you miss the timing, right-click on your VM's name on the left to shutdown and reboot your VM) 
</p>
<h3> 
Applying Windows Server 2022 and reaching the desktop of our VM
</h3>
<br />
<p>
  When your VM boots up, select your language and select "Next".
</p>
<p>
  <img src="https://i.imgur.com/i61WQKi.jpg" height="75%" width="100%" alt="Sys admin agent login"/>
</p>
<p>
  The next pop-up will ask you to select the OS you wish to install. Select "Windows Server 2022 Standard Evaluation (Desktop Experience)" and then press "Next" to continue.
  <img src="">
</p>
<p>
 It will ask which type of installation you want, select "Custom" and then select "Next".
</p>
<p>
  <img src="https://i.imgur.com/DYPJufr.png" height="75%" width="100%" alt="Working the issue"/>
</p>
<br />
<p>
 The next screen will show the drives' Unallocated Space,make sure the 20.0 GB we previously set matches for both "Total Size" and "Free Space".
  Allow the installation to complete, this may take a few minutes, once complete your VM instance will restart to apply the changes.
<img src="">
</p>
<p>
  Once your VM restarts, you may choose a password for the Admin account (This will be the "main" account given the permissions to create the Active Directory)
  <img src="">
</p>
<p> 
  Once password is set, Log in to your Admin account to finally see your VM desktop! ( To check if Windows Server 2022 has been downloaded, go to the bottom left search bar and type "winver")
</p>
<br />
<h2>Active Directory Setup</h2>
<br />
<p>
This next section will focus on creating our Active Directory from scratch.
</p>
<h3 align="center">Server Manager Setup</h3>
<p>
  When you first load into the desktop of your VM environment, an application named "Server Manager" will appear. On Server Manager's dashboard, click "Manage" then "Add Roles and Features".
  <img src="https://i.imgur.com/kRpUysm.png" height="75%" width="100%" alt="Working the issue"/>
</p>
<br />
<p>
 Once you reach the "Add Roles and Features Wizard, click "Next" until you get to the "Server Roles" portion. Select "DNS Server".
  <img src="">
</p>
<p>
  Click "Next" to reach the "Features" portion and make sure you have "Group Policy Management" checked. Then click "Next" until you have reached "Confirmation" to install. This may take a few minutes, do not close the tab.
  <img src="">
</p>
<p>
When this has been installed, on the same page under " Active Directory Domain Services" click the blue line that says " Promote this server to a domain controller". 
</p>
<p>
  The new window should be titled "Deployment Configuration" where you will select the bullet point "Add a new forest", and name your Root domain name whatever you see fit, followed by ".local". Click "Next" when you are done.
  <img src="">
</p>
<p>
  On the next portion, select your Forest and Domain functional level to be Windows Server 2016 for both. Then input a password you will remember. 
  <img src="">
</p>
<p>
  Click "Next" when you are done with the previous step until you reach "Prerequisites check" Once this has been completed you are able to then click Install. This may take a few minutes, and will restart your VM to apply the changes.
</p>

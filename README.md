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
  <img src="https://i.imgur.com/zWMLl48.png" height="75%" width="100%">
  <br />
<h3 align="center"> Downloading VMware Workstation Pro</h3>
<p>
Download Version 17.5.2
  <img src="https://i.imgur.com/iKNVxtt.png: height="75%" width="100%" alt="O"/>
</p>
<br/>
<p>
  When you double-click the download pop-up and follow the instructions the setup wizard displays, make sure to select "Personal Use" at the end. 
</p>
<br />
<br />
<h3 align="center">Downloading Windows Server 2022</h3>
<br />
<p>
  Click the second link under "Helpful Links" to be sent to the download website.
</p>
<p>
  <img src="https://i.imgur.com/VeOLWCF.png" height="75%" width="100%" alt="Support agent login"/>
</p>
<br />
<br />
<h2>Virtual Machine Boot Up</h2>
<br />
<p>
  The focus for the next portion will be booting up our Virtual Machine and configuring the Windows Server on VMware Workstation Pro
</p>
<h3 align="center">Creating a New Virtual Machine</h3>
<br />
<p>
When you load VMware Workstation Pro, you will view a screen with three selections. Pick the left-most that says "Create a New Virtual Machine"
  <img src="https://i.imgur.com/LaYs48E.png">
</p>
<br/>
<p>
The Virtual Machine Wizard will show, click next and select "I will install the operating system later," then hit next. We will use the Windows Server 2022 download for this section later. 
  <img src="https://i.imgur.com/KTLsX5P.png">
</p>
<br/>
<p>
Select the guest OS as Microsoft Windows, then click the "Version" tab and select "Windows Server 2022", then hit Next. 
  <img src="https://i.imgur.com/21rCQZ1.png">
</p>
<br/>
<p>
For the next section, you may name your VM however you see fit, then select Next.
</p>
<p> 
For Specific Disk Capacity, change the Maximum disk size to "20GB" and select Next to officially create your Virtual Instance!
  <img src="https://i.imgur.com/lCVfgOp.png">
</p>
<br/>
<p>
Once you view a blank screen, which is your powered-off VM, right-click whatever you named your VM on the left tab and go to CD/DVD (SATA). Then, click the "use ISO image file" to select your Windows Server 2022 file.  
  <img src="https://i.imgur.com/4es3b2e.png">
</p>
<br/>
<p>
  Then, select "Ok" to load your ISO and power on your Virtual Machine! (Important: When you view the message "Press any key to boot from CD or DVD" click any button to avoid issues with the bootup. If you miss the timing, right-click on your VM's name on the left to shutdown and reboot your VM) 
</p>
<h3> 
Applying Windows Server 2022 and reaching the desktop of our VM
</h3>
<br />
<p>
  When your VM boots up, select your language and select "Next".
</p>
<p>
  The next pop-up will ask you to select the OS you wish to install. Select "Windows Server 2022 Standard Evaluation (Desktop Experience)" and then press "Next" to continue.
  <img src="https://i.imgur.com/21rCQZ1.png">
</p>
<br/>
<p>
 It will ask which type of installation you want, select "Custom" and then select "Next".
</p>
<p>
  <img src="https://i.imgur.com/dDGgL6A.png">
</p>
<br />
<p>
 The next screen will show the drives' Unallocated Space. Make sure the 20.0 GB we previously set matches for both "Total Size" and "Free Space".
  Allow the installation to complete, this may take a few minutes. Once complete, your VM instance will restart to apply the changes.
<br/>
<img src="https://i.imgur.com/D4JFFXt.png">
</p>
<br/>
<p>
  Once your VM restarts, you may choose a password for the Admin account (This will be the "main" account given the permissions to create the Active Directory)
  <img src="https://i.imgur.com/tnpeAyf.png">
</p>
<p> 
  Once a password is set, log in to your Admin account to see your VM desktop! ( To check if Windows Server 2022 has been downloaded, go to the bottom left search bar and type "winver")
</p>
<br />
<h2>Active Directory Setup</h2>
<br />
<p>
This next section will focus on creating our Active Directory from scratch.
</p>
<h3 align="center">Server Manager Setup</h3>
<p>
  When you first log into the desktop of your VM environment, an application named "Server Manager" will appear. On Server Manager's dashboard, click "Manage" then "Add Roles and Features".
  <img src="https://i.imgur.com/vV8ipNp.png" height="75%" width="100%">
</p>
<br />
<p>
 Once you reach the "Add Roles and Features Wizard, click "Next" until you get to the "Server Roles" portion. Select "DNS Server".
  <img src="https://i.imgur.com/VAQAqNa.png">
</p>
<p>
  Click "Next" to reach the "Features" portion and make sure you have "Group Policy Management" checked. Then click "Next" until you have reached "Confirmation" to install. This may take a few minutes; do not close the tab.
  <br/>
  <img src="https://i.imgur.com/dCjVRpC.png">
  Group Policy Checkbox.
  <img src="https://i.imgur.com/ntQkxAM.png">
  Installation.
</p>
<p>
When this has been installed, on the same page under " Active Directory Domain Services," click the blue line that says " Promote this server to a domain controller". 
</p>
<p>
  The new window should be titled "Deployment Configuration" where you will select the bullet point "Add a new forest", and name your Root domain name whatever you see fit, followed by ".local". Click "Next" when you are done.
  <img src="https://i.imgur.com/mN2Wid2.png">
</p>
<p>
  On the next portion, select your Forest and Domain functional level to be Windows Server 2016 for both. Then input a password you will remember. 
  <img src="https://i.imgur.com/HWJ45x4.png">
</p>
<p>
  Click "Next" when you are done with the previous step until you reach "Prerequisites check" Once this has been completed, you are able to then click Install. This may take a few minutes and will restart your VM to apply the changes.
  <img src="https://i.imgur.com/zlY59xC.png">
</p>
<br/>
<h2>Setting up AD for a fictional company</h2>
<br/> 
<p>
  The final section will be setting up OUs, groups/group types, and users for a fictional company. 
</p>
<h3 align="center"> Creating OUs</h3> 
<br/>
<p> 
  After you have installed, reset, and logged into your account (Note: the account will be associated with your Domain name, followed by "Administrator"). Go into the Windows search bar to find "Active Directory Users and Computers". 
  <img src="https://i.imgur.com/LZEYNck.png">
</p>
<p>
  Once in the application, right-click on your ____.local domain we created before, and hover over "New" and select "Organizational Unit".It will bring a text box, where you can name it whatever you'd like. In this example, I called three separate OUs "USA", "Europe",and "Asia. 
 <img src="https://i.imgur.com/OJ0K9FP.png">
</p>
<p>
  To simulate a typical work environment, I created three OU's within these three OU's. I named these OU's "Computer", "Users", and "Server". 
  <img src="https://i.imgur.com/sl4dyZJ.png">
</p>
<br/>
<h3 align="center"> Creating Groups under Sub OUs and selecting appropriate Group Types.</h3>
<p>
  This step follows a similar flow to creating an OU. Feel free to use these steps to format your own Active Directory to your liking. First, enter an OU you have created and right-click on the sub-OU "Users", then select "Group" where you will name the group "IT".
  <img src="https://i.imgur.com/H1TUxD2.png">
</p>
<p>
  Next, create another sub-OU with the title " DL-ITAdmins", "DL" being short for "Distribution List". For group type, we will select "Distribution", not "Security". 
  <img src="https://i.imgur.com/QiN4XtI.png">
</p>

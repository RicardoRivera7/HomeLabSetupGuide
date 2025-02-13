<h1>HomeLab Setup Guide including IDS</h1>


<h2>Description</h2>
A guide to show how to start a homelab utilzing your prefered OS and adding an IDS
<br />

<h2>Prerequisites</h2>
- <b>None</b> 

<h2>Software Used</h2>

- <b>Virtualbox </b> 

<h2>Environments Used </h2>

- <b>Linux</b>
- <b>Windows 10/11</b>
- <b>Security Onion IDS</b>

<h2>Downloads</h2>

-[Virtualbox](https://www.virtualbox.org/wiki/Downloads)
<br/>
-[Security Onion IDS](https://github.com/Security-Onion-Solutions/securityonion/blob/2.4/main/DOWNLOAD_AND_VERIFY_ISO.md)
<br/>
-[Ubuntu Linux ISO](https://ubuntu.com/download/desktop) 
<br/>
-[Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10)
<br/>
-[Windows 11 ISO](https://www.microsoft.com/en-us/software-download/windows11)



<h2>Setup Walk-through:</h2>

<p align="left">
Download Virtual box and an ISO of your choice <br/> 
Go through the Virtualbox installation Wizard (you can choose all default options): <br/>
To begin creating a new machine click on the New button 
<img src="https://i.imgur.com/i4ayIkD.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Enter any name you want for example if you're using the ubuntu iso type in ubuntu  <br/>
In the iso image section select where you downloaded your iso <br/>
<img src="https://i.imgur.com/p3QIkZL.png" height="80%" width="80%" alt="Firewall Steps"/> 
<br/>
<br/>
In the hardware tab make sure to allocate at least 1gb of memory (1000 mb) and as many processors as you want <br/>
<img src="https://i.imgur.com/gfkJxew.png" height="80%" width="80%" alt="Firewall Steps"/> 
<br/>
<br/>
In the hard disk tab allocate at least 99gb and click finish (this will launch the Ubuntu installation) <br/>
<img src="https://i.imgur.com/PZ3MNbx.png" height="80%" width="80%" alt="Firewall Steps"/> 
<br />
<br />
Once done login to your virtual machine (default password is changeme if you put a password on) <br/>
<img src="https://i.imgur.com/fncBWS0.png" height="80%" width="80%" alt="Firewall Steps"/>
<br/>
<br/>
  
<h2>Security Onion IDS installation:</h2>

<p align="left">
Download the Security Onion ISO and follow the steps from the previous section to create a new machine <br/>
Once you click finish this will begin the installation process but will be aborted <br/> 
<img src="https://i.imgur.com/4lvnJMo.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
We will need to mount the iso to the machines storage: <br/>
Select the machine and click settings <br/>
Click on the storage tab <br/>
Under the Controller: IDE section click on the disk that says unattended <br/>
On the line that says Optical drive click on the disk with an arrow icon and select your security onion iso <br/> 
<img src="https://i.imgur.com/DuVt0px.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Click the start button to begin the installation <br/>
It will prompt you to type yes if you want to continue, type yes and enter any admin name and password you want <br/>
Wait for the installation process to complete then login with the admin name and password you created <br/>
<img src="https://i.imgur.com/6kqS24I.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<img src="https://i.imgur.com/1tYim7v.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Start the Virtual Machine and start the installation <br/>
<img src="https://i.imgur.com/BmDRGKu.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Choose all the default options and make sure you select the checkbox for the ZFS Configuration section:  <br/>
<img src="https://i.imgur.com/VZVpugG.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Select Yes for the next option and wait until installation is complete, once you get the complete box you must unmount the ISO or it will cycle through the boot process again:  <br/>
At the top bar of the Virtualbox go to Devices -> Optical Drives -> select your pfsense ISO -> Click Force Unmount <br/>
Click Reboot <br/>
<img src="https://i.imgur.com/io57SG0.png" height="80%" width="80%" alt="Firewall Steps"/>
<br />
<br />
Create and install another virtual machine for Linux or Windows whichever you prefer (I used Linux)  <br/>
Edit the adapter 1 to be Attached to Internal Network and launch the new VM <br/>
Open the command line and type ifconfig (linux) or ipconfig (windows) <br/>
Check to see that the inet ip matches your LAN ip thats on PFsense 
<img src="https://i.imgur.com/9rRPKPU.png" height="80%" width="80%" alt="Firewall Steps"/>
<br/>
<img src="https://i.imgur.com/GA4Rpbg.png" height="80%" width="80%" alt="Firewall Steps"/>
<br/>
<br/>
You can try to ping the LAN ip in the command line to see if you get a response back <br/>
<img src="https://i.imgur.com/u3qFSN0.png" height="80%" width="80%" alt="Firewall Steps"/>
<br/>
<br/>
Open a web browser and type in the LAN ip, you will get a warning since there is no certificate, you can just ignore that an advance <br/>
<img src="https://i.imgur.com/AP54rb3.png" height="80%" width="80%" alt="Firewall Steps"/> 
<br/>
<br/>
Login using the default credentials all lowercase for the username and password: <br/> 
Username is admin <br/>
Password is pfsense <br/>
<img src="https://i.imgur.com/nhHiR0V.png" height="80%" width="80%" alt="Firewall Steps"/>  
<br/>
<br/>
Go through the installation wizard and then you have your firewall all setup using pfsense!

  
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

<h1>Vulnerability Management: Nessus Essentials</h1>
<img src="https://imgur.com/nKKY5if.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h2>Description</h2>
We are going to address vulnerability remediation and scanning in this project. The Vulnerability Management Lifecycle consists of these two key components. In order to execute credentialed scans to find vulnerabilities, fix some of the vulnerabilities, and then run another scan to confirm remediation, we will be utilizing Nessus Essentials to scan local virtual machines (VMs) hosted on VMware Workstation. 
<br />


<h2>Languages and Utilities Used</h2>

- <b>Nessus Essentials</b> 
- <b>Windows 10 ISO</b>

<h2>Environments Used </h2>

- <b>VMware Workstation Player</b>
- <b>Windows 10</b> (21H2)
- <b>Server 2019</b>

<h2>Program walk-through:</h2>

<p align="center">
Download VMware Player: <br/>
<img src="https://imgur.com/agzJ2ag.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download Windows 10 ISO:  <br/>
<img src="https://imgur.com/wf3zP0r.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download Nessus Essentials: <br/>
<img src="https://imgur.com/Pc5OCii.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set up Windows 10 ISO and create an ISO file:  <br/>
<img src="https://imgur.com/H0Xp8qP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Set up the Windows 10 VM and browse to the ISO file we created:  <br/>
<img src="https://imgur.com/LRPY75i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
When setting up the virtual machine, in the hardware settings under network adapters, choose bridged (this allows the VM and the actual PC be on the same network, making it easier for nessus essentials to scan:  <br/>
<img src="https://imgur.com/MaWhCne.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Boot Window 10 VM and set up:  <br/>
<img src="https://imgur.com/GtkwC7P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Get the IPv4 address on the VM and Ping it on your actual PC:  <br/>
<img src="https://imgur.com/rlhAjlU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
You will notice that the ping will time out, this is due to the firewalls on the VM:  <br/>
<img src="https://imgur.com/sRUeaSA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Disable the firewalls in the WIndow Firewall Defender then ping again:  <br/>
<img src="https://imgur.com/zOoXbmX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/UWgUFsy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In Nessus Essentials, create a new network scan:  <br/>
<img src="https://imgur.com/qYv2pwY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After the network scan is created, inspect the first scan with no credentials:  <br/>
<img src="https://imgur.com/SWnkvh6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
On the virtual Machine, open up servcies and enable Remote Registry which will allow the scanner to connect to this VMs registry to look for insecure configurations: <br/>
<img src="https://imgur.com/fLcgb9q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enable File and Printer Sharing on the VM:  <br/>
<img src="https://imgur.com/apJfNNt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to User Account Control and change to never notify:  <br/>
<img src="https://imgur.com/cSRcGcb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Go to Registry Editor and in the directory below (Found on Nessus) create a DWORD file with the following name and set the value data to 1. Restart the VM:  <br/>
<img src="https://imgur.com/Oqsfovw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
At this point of the project, we are ready to scan the VM. Go to Nessus Essentials now and add the following credentials. Hit save:  <br/>
<img src="https://imgur.com/1S592gZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After letting it run for a bit, you can see the difference in vulnerbilities before and after adding credentials:  <br/>
<br />
BEFORE:  <br/>
<img src="https://imgur.com/weZuPFh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
AFTER:  <br/>
<img src="https://imgur.com/KknbiJj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After taking a deeper dive into the vulnerabilities, you can see how Nessus Essentials provides solutions for critical vulnerabilities like the one shown below:  <br/>
<img src="https://imgur.com/qolQ1CF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Download a very old version of firefox just to run another scan with more vulnerabilities before we start remediating:  <br/>
<img src="https://imgur.com/qMW7B4j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Launch the scan once again for a bit and come back to the vulnerablities and you should see something like this:  <br/>
<img src="https://imgur.com/DooiCzC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/69EWLLb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After reading the remediations, update and restart windows on the VM:  <br/>
<img src="https://imgur.com/SwPAmyP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now run the scan once more and observe how the vulnerabilities and remediations decrease:  <br/>
<img src="https://imgur.com/l2iOPoe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
This concludes the project on how to manage vulnerabilites using Nessus Essentials!  <br/>



</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!># scan

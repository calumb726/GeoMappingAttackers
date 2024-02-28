# GeoMappingAttackers



<h2>Description</h2>
launching a virtual machine (HoneyPot), Take down security measures and leave the machine bare and open to the internet. I will then use log data of malicious actors trying to gain access to my machine through failed log in attemts, I will convert their ip address into longitude and latitude quardinates and use this to plot a geographical map of where the atttacks are coming from globaly and te volume of attacks.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
<h2>Program walk-through:</h2>

<p align="center">
Launch the virtual machine with low security protocals to the machine visible to threat actors: <br/>
<img src="https://imgur.com/N09RCjL.png" height="80%" width="80%" />
<br />
<br />
Create log analytic workspace:  <br/>
<img src="https://imgur.com/3GCsosk.png" height="80%" width="80%" />
<br />
<br />
Enable ability to gather logs from the VM into the log analytic workspace<br/>
<img src="https://imgur.com/o3xK0Od.png" height="80%" width="80%" />
  <img src="https://imgur.com/wpibgmr.png" height="80%" width="80%" />
<br />
<br />
connect VM to LAW:  <br/>
<img src="https://imgur.com/RaM3Eom.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
add microsoft sentinal to the law:  <br/>
<img src="https://imgur.com/y4lzBHP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log into virtual machine and disable firewalls:  <br/>
<img src="https://imgur.com/xWMnJRV.png" height="80%" width="80%" />
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

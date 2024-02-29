# GeoMappingAttackers



<h2>Description</h2>
launching a virtual machine (HoneyPot) and taking down security measures to leave the machine bare and open to the internet. I will then use log data of malicious actors trying to gain access to my machine through failed log in attemts, I will convert their ip address into longitude and latitude Coordinates and use this to plot a geographical map of where the atttacks are coming from globaly aswell as how many log in attempts have been made from each location.
<br/>
<img src="https://imgur.com/gw87eAx.png" height="50%" width="50%" />
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Azure</b>
- <b>SIEM</b>
- <b>Event viewer</b>
- <b>Log Analysis</b>
- <b>Virtual Machine</b>



<h2>Program walk-through:</h2>

<p align="center">
Launch the virtual machine with low security protocals <br/>
<img src="https://imgur.com/N09RCjL.png" height="50%" width="50%" />
<br />
<br />
Create log analytic workspace  <br/>
<img src="https://imgur.com/3GCsosk.png" height="50%" width="50%" />
<br />
<br />
Enable ability to gather logs from the VM into the log analytic workspace<br/>
<img src="https://imgur.com/o3xK0Od.png" height="50%" width="50%" />
  <img src="https://imgur.com/wpibgmr.png"  height="50%" width="50%" />
<br />
<br />
connect VM to LAW  <br/>
<img src="https://imgur.com/RaM3Eom.png" height="50%" width="50%" />
<br />
<br />
add microsoft sentinal to the la  <br/>
<img src="https://imgur.com/y4lzBHP.png" height="50%" width="50%" />
<br />
<br />
Log into virtual machine and disable firewalls  <br/>
<img src="https://imgur.com/xWMnJRV.png"  height="50%" width="50%" />
<br />
<br />
here i copied this powershell scrip from this git hub reposotory into Powershel ISE on the VM to parse the data collected from the windows event log on the VM, this uses an API to obtai a longitude and latitude from the ip adderss-This is how we will get a precise location  <br/>
<img src="https://imgur.com/pJ19cp6.png"  height="50%" width="50%" />
  <img src="https://imgur.com/xfFl3RO.png"  height="50%" width="50%" />
  <br />
  Create a new MMA based table in your log analysis workspace: <br/>
<img src="https://imgur.com/b0BHX6z.png" height="50%" width="50%" />
  <br />
next we need to upload the file created by the powershell code into the table, The file created by powershell is saved on our VM however the azure page which contains the table is on our native machine this means we must copy the contents of the file and recreate the file on our native machine. Once this is done we can add the file from our native machine. It is important to note that when asked for the file path on the next page you give the file path of the origional file on the VM, This is because that list is being constantly updated and will be the one accessed by the table. The first file we moved over is so we can 'Train' the table how to read the infomation, this will become clear in the next few steps.  
  <br/>
  <img src="https://imgur.com/b0BHX6z.png"  height="50%" width="50%" />
  <img src="https://imgur.com/TDyQD6x.png"  height="50%" width="50%" />
  <br />
  Next i had to sort the data in the log and seperate the fields. <br/>before:
  <br/>
    <img src="https://imgur.com/EcCKiN7.png"  height="50%" width="50%" />
  <br/>
  after:
  <br/>
  <img src="https://imgur.com/lKChtx9.png"  height="50%" width="50%" />
  <br/>
  In microsoft sentinal open up a new workbook and enter the same query as before
  <br/>
    <img src="https://imgur.com/UC0Bf4W.png"  height="50%" width="50%" />
  <br/>
  <br/>
  change the view type to map and change settings to desire
  <br/>
     <img src="https://imgur.com/mCc7xuk.png"  height="50%" width="50%" />
     
  <br/>
  here is the map after a few hours
  <br/>
     <img src="https://imgur.com/gw87eAx.png"  height="50%" width="50%" />
  
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

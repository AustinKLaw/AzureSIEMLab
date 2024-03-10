# AzureSIEMLab
Creating a honeypot in Microsoft Azure

<h1>Honeypot with Microsoft Sentinel</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
I created a honeypot in Microsoft Azure by removing all firewall rules and opening all the ports to the internet. I monitored and logged Remote Desktop login attempts and brute force attacks using Microsoft Sentinel log management. I plotted them in real time using geolocation data from the logs on a map. After leaving it exposed for a while, I defended against brute force attacks by changing the RDP port, using software to lockout IPs and locations, and then enabling multifactor authentication.
<br />


<h2>Utilities Used</h2>

- <b>Azure</b> 
- <b>Sentinel</b>
- <b>IP Geolocation API</b>
- <b>RDP Guard</b>
- <b>Duo</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Opening Ports In Azure: <br/>
<img src="https://i.imgur.com/601wlsD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

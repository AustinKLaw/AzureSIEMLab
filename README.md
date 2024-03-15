<h1>Honeypot with Microsoft Sentinel</h1>

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

<h2>Opening Up the VM:</h2>

<p align="center">
Opening Ports In Azure: <br/>
<img src="https://i.imgur.com/Pu0xl9v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
First Ping Attempt:  <br/>
<img src="https://i.imgur.com/giyoXnQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Disabling Firewall and Sending Ping: <br/>
<img src="https://i.imgur.com/Lvuqaqn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Querying Logs In Sentinel:  <br/>
<img src="https://i.imgur.com/0Ydh0so.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Map After 1 Hour (Russia Attacks):  <br/>
<img src="https://i.imgur.com/Qyosh2v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2>Initial Thoughts</h2>
Almost as soon as the machine was vulnerable login attemtps came in. We can see the login attempts use very simple default usernames and passwords, since there are no indication of usernames on the machine. Russia overwhelmed the machine so much that within a few hours all of my free API requests for geolocation were used, so I unfortunately didn't get to plot any other countries. This bearing in mind is only the brute force RDP connections, and doesn't list any other network interactions.

<h2>Stopping Attacks</h2>
<p align="center">
Changed RDP Port, still had brute force attacks: <br/>
<img src="https://i.imgur.com/1PTQjxT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Misconfigured setup and got locked out:  <br/>
<img src="https://i.imgur.com/PDcRrPK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Adding My IP Address To Whitelist: <br/>
<img src="https://i.imgur.com/symDbZC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Using Geolocation to Block Address:  <br/>
<img src="https://i.imgur.com/zq8ePa6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Connecting Back To US:  <br/>
<img src="https://i.imgur.com/0UigFD3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Setup 2FA To Block Anyone With Password:  <br/>
<img src="https://i.imgur.com/L7WcXwL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2>Conclusion</h2>
I thought going into this that reconfiguring the default port addresses would be a more helpful deterrent. However it had almost no decrease on the barrage of login attempts. I had a bit of a scare misconfiguring geolocation blocker and locking myself out of the machine, but was able to use the console to whitelist my IP and regain access. A firewall can block a connection but if someone has a backdoor they will be able to regain access easily! The geolocation worked great once setup and reduced a lot of attacks, however using a VPN can easily bypass this. A private VPN would be far more effective, and 2FA helps ensure that even if there is a brute-force attack that nobody has access to the system who isn't approved.

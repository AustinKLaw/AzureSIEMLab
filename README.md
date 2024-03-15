<h1>Vulnerabilty Scanning and Analysis with Nessus</h1>

<h2>Description</h2>
I grabbed a vulnerable machine off the web, Metasploitable v2, and scanned it using Nessus to see what sort of weaknesses I'd find.
<br />


<h2>Utilities Used</h2>

- <b>VMWare</b> 
- <b>Nessus</b>
- <b>Metasploitable</b>

<h2>Environments Used </h2>

- <b>Ubuntu VM</b>
- <b>Windows 11</b>

<h2>Metasploitable Scans:</h2>

<p align="center">
Launching the machine: <br/>
<img src="https://i.imgur.com/oW8aM4U.png"/>
<br />
<br />
Scan with Nessus:  <br/>
<img src="https://i.imgur.com/jaSk8Gs.png"/>
<br />
<br />
Deprecated Ubuntu Version: <br/>
<img src="https://i.imgur.com/oDoaQ8a.png"/>
<br />
<br />
Unpatched DNS Resolver:  <br/>
<img src="https://i.imgur.com/179fnaq.png"/>
<br />
<br />
SSL 2.0/3.0 Protocol:  <br/>
<img src="https://i.imgur.com/bdiqy44.png"/>
<br />
<br />
Weak Passwords:  <br/>
<img src="https://i.imgur.com/VymRJik.png"/>
<br />
<br />
Keys Generated with bugged libraries:  <br/>
<img src="https://i.imgur.com/1xQcMdL.png"/>
</p>

<h2>Analysis</h2>
Since this machine has a large amoutn of vulnerabilites that need to be resolved, it would be a major liability to any company whose network its on. While doing this testing, this VM was only exposed to my local network, so there was no risk of infection or VM escape. 
With a machine this insecure, it would be worth scanning to see if it had been compromised, and if so following NIST 800-61 Incident Response lifecyle. If there wasn't any confirmed breaches, I'd create a detailed report of the most critical flaws to hand to any teams dependent on this system, so we could work together to resolve them without reducing productivity. In particular it would likely be worth educating on password usage, given the amount of default passwords used that could be brute forced on the open ports. Once all critical vulnerabilities were addressed we could move towards resolving less major issues, and creating plans and systems to keep the machine updated, as well as any other machines with out of date software.

It also makes sense to automate this scanning process with Nessus or any other solution due to making it easier to identify vulnerabilites and deprecated software as they appear, and making resolution of such issues less time critical and less likely to interrupt workflows.


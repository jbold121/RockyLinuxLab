<h1>Harden Rocky Linux to CIS Benchmark</h1>

<h2>Description</h2>
Project demonstrates the hardening of a Rocky Linux 10 minimal server to CIS Level 1 standards using OpenSCAP. A baseline compliance scan was performed, targeted remediation was applied, and post-remediation validation confirmed improved security posture. Advanced security controls were then implemented, including SSH key-only authentication, auditd process execution logging, firewall segmentation, file integrity monitoring (AIDE), and centralized logging preparation.

This project simulates enterprise Linux server hardening and security engineering practices.
<br />


<h2>Languages and Utilities Used</h2>

- <b>OpenSCAP</b> 
- <b>SSH</b>
- <b>firewalld</b>
- <b>auditd</b>
- <b>AIDE</b>
- <b>Bash scripting</b>

<h2>Environments Used </h2>

- <b>Rocky Linux 10 (Minimal Install)</b>

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

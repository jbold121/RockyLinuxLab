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

System Update <br/>
<p align="center"> Update the system to ensure all packages are current before performing compliance scanning. <br/> <img src="images/update (1).png" height="40%" width="40%" alt="System Update" /> <br /><br /> </p>
<p align="center"> Install OpenSCAP scanner and SCAP Security Guide content required for CIS evaluation. <br/> <img src="images/scap install (2).png" height="70%" width="70%" alt="OpenSCAP Installation" /> <br /> <img src="images/scap install 2 (3).png" height="80%" width="80%" alt="OpenSCAP Installation Complete" /> <br /><br /> </p>
<p align="center"> Inspect available compliance profiles within the SCAP datastream. <br/> <img src="images/search profiles (4).png" height="80%" width="80%" alt="Search CIS Profiles" /> <br /><br /> </p>
<p align="center"> Execute initial CIS Level 1 scan to establish compliance baseline. <br/> <img src="images/baseline scan (5).png" height="100%" width="100%" alt="CIS Baseline Scan" /> <br /><br /> </p>
<p align="center"> Baseline report showing 116 failed rules and ~79% compliance score prior to remediation. <br/> <img src="images/scan report html (6).png" height="80%" width="80%" alt="Baseline HTML Report" /> <br /><br /> </p>
<p align="center"> Generate automated remediation script for CIS Level 1 profile. <br/> <img src="images/remediation script (7).png" height="100%" width="100%" alt="Generate Remediation Script" /> <br /><br /> </p>
<p align="center"> Generate list of SSH rules for custom SSH remediation script <br/> <img src="images/ssh rules.png" height="100%" width="100%" alt="Generate Remediation Script" /> <br /><br /> </p>
<p align="center"> Generate ed25519 key pair for secure SSH key-only authentication and deploy to authorized_keys <br/> <img src="images/ssh key gen.png" height="60%" width="60%" alt="SSH Key Generation" /> <br /><br /> </p>
<p align="center"> Execute custom SSH-only remediation script derived from full CIS remediation output. <br/> <img src="images/ssh-eval script (12).png" height="60%" width="60%" alt="SSH Remediation Script Execution" /> <br /><br /> </p>
<p align="center"> Results from SSH-only remediation script <br/> <img src="images/ssh eval (13).png" height="60%" width="60%" alt="SSH Key Generation" /> <br /><br /> </p>
<p align="center"> Verify SSH access post-remediation. <br/> <img src="images/ssh access post rem(10).png" height="50%" width="50%" alt="SSH Access Post Remediation" /> <br /><br /> </p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

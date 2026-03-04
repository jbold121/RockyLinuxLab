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

<p align ="center"> 1. OpenSCAP and SSH </p> <br/>
<p align="center"> Update the system to ensure all packages are current before performing compliance scanning. <br/> <img src="images/update (1).png" height="40%" width="40%" /> <br /><br /> </p>
<p align="center"> Install OpenSCAP scanner and SCAP Security Guide content required for CIS evaluation. <br/> <img src="images/scap install (2).png" height="70%" width="70%" alt="OpenSCAP Installation" /> <br /> <img src="images/scap install 2 (3).png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Inspect available compliance profiles within the SCAP datastream. <br/> <img src="images/search profiles (4).png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Execute initial CIS Level 1 scan to establish compliance baseline. <br/> <img src="images/baseline scan (5).png" height="100%" width="100%" /> <br /><br /> </p>
<p align="center"> Baseline report showing 116 failed rules and ~79% compliance score prior to remediation. <br/> <img src="images/scan report html (6).png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Generate automated remediation script for CIS Level 1 profile. <br/> <img src="images/remediation script (7).png" height="100%" width="100%" /> <br /><br /> </p>
<p align="center"> Generate list of SSH rules for custom SSH remediation script <br/> <img src="images/ssh rules.png" height="100%" width="100%" /> <br /><br /> </p>
<p align="center"> Generate ed25519 key pair for secure SSH key-only authentication and deploy to authorized_keys <br/> <img src="images/ssh key gen.png" height="60%" width="60%" alt="SSH Key Generation" /> <br /><br /> </p>
<p align="center"> Execute custom SSH-only remediation script derived from full CIS remediation output. <br/> <img src="images/ssh-eval script (12).png" height="60%" width="60%" alt="SSH Remediation Script Execution" /> <br /><br /> </p>
<p align="center"> Results from SSH-only remediation script <br/> <img src="images/ssh eval (13).png" height="60%" width="60%" /> <br /><br /> </p>
<p align="center"> Verify SSH access post-remediation. <br/> <img src="images/ssh access post rem(10).png" height="50%" width="50%" /> <br /><br /> </p>

<p align ="center"> 2. Auditd </p> <br/>

<p align="center"> Verify auditd service status <br/> <img src="images/auditd status.png" height="80%" width="80%"/> <br /><br /> </p>
<p align="center"> Configure log retention <br/> <img src="images/log retention conf.png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Create dedicated file with rules <br/> <img src="images/cis rules.png" height="60%" width="60%" /> <br /><br /> </p>
<p align="center"> Create rule set <br/> <img src="images/auditd rules.png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Load rule set <br/> <img src="images/augenrules load.png" height="50%" width="50%" /> <br /><br /> </p>
<p align="center"> Verify rules are laoded <br/> <img src="images/verify audit rules.png" height="80%" width="80%" /> <br /><br /> </p>
<p align="center"> Test rules by creating events <br/> <img src="images/test rules 1.png" height="60%" width="60%" /> <br /><br /> </p>
<p align="center"> Search events <br/> <img src="images/test rules 2.png" height="60%" width="60%" /> <br /> </p>
<p align="center"> <img src="images/test rules 3.png" height="80%" width="80%" /> <br /><br /> </p>

<p align ="center"> 3. AIDE </p> <br/>

<p align="center"> Install AIDE <br/> <img src="images/install.png" height="80%" width="80%"/> <br /> </p>
<p align="center"> Create systemd service and timer file for scheduled checks <br/> <img src="images/create service file.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> <img src="images/service file.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> <img src="images/create timer file.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> <img src="images/timer file.png" height="80%" width="80%" /> <br /> <br /> </p>
<p align="center"> Configure AIDE to verify audit tools <br/> <img src="images/aide conf.png" height="60%" width="60%" /> <br /> </p>
<p align="center"> <img src="images/verify audit tools.png" height="60%" width="60%" /> <br /> <br /> </p>
<p align="center"> Enable and start service <br/> <img src="images/timer and service verification.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Initialize AIDE scan and promote the new database <br/> <img src="images/initialize.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> <img src="images/promote.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Test a check against the new database <br/> <img src="images/check.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Testing the evaluation of AIDE rules show two were remediated, while verifying audit tools and crontab failed <br/> <img src="images/aide eval 1.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Rsyslogd rule was missing, so I added an rsyslogd rule to aide.conf <br/> <img src="images/verify audit tools 2.png" height="50%" width="50%" /> <br /> </p>
<p align="center"> Although I created a timer using systemd, the OSCAP rule is looking for a root crontab entry <br/> <img src="images/chrontab.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Evaluated the AIDE rules again, this time with a pass <br/> <img src="images/aide eval 2.png" height="80%" width="80%" /> <br /> <br /> </p>

<p align ="center"> 4. Firewalld </p> <br/>

<p align="center"> Check firewalld status <br/> <img src="images/firewalld status.png" height="80%" width="80%"/> <br /> </p>
<p align="center"> Remove unnecessary services (cockpit and dhcpv6) <br/> <img src="images/remove service.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Configure the lo interface to be in the trusted zone, and deny loopback address traffic from any other interface <br/> <img src="images/firewalld rules.png" height="80%" width="80%" /> <br /> </p>
<p align="center"> Evaluate firewalld results <br/> <img src="images/firewalld eval.png" height="80%" width="80%" /> <br /> </p>





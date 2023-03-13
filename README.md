<p align="center">
<img src="https://i.imgur.com/pgYpTCl.png" alt="Traffic Examination"/>
</p>

<h1Basic configuration of A-records and CNAME records</h1>
In this explanation an Azure Virtual Machine running Microsoft Active Directory will be used to configure A-records and CNAME records and observe the changes. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Created the environments for the traffic to be examined in
- Downloaded network traffic viewing software within Virtual Machine
- Began triggering traffic over different network protocols and filtering to see each protocol

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/Og23TWf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first step was to create the environments to begin the network traffic inspection, in this case it was a Windows 10 Virtual machine and a Linux Ubuntu Virtual Server.
</p>
<br />

<p>
<img src="https://i.imgur.com/rq532Sx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Downloaded and installed WireShark and then began inspecting the traffic created by a simple ping command in Windows PowerShell to the Linux Ubuntu server and filtering for ICMP traffic sent and received from the ping command.
</p>
<br />

<p>
<img src="https://i.imgur.com/DQgGU0y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I then went into the Windows Virtual machines Network Security Group within Azure (Network Security Groups have a similar function to firewalls) and created a rule to deny inbound and outbound ICMP traffic.
</p>
<br />

<p>
<img src="https://i.imgur.com/zhxEEAc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upon creation of the traffic denial rule it was clearly shown in PowerShell as well as WireShark that the Virtual Machine could no longer communicate via ICMP. Deleting the NSG rule allowed the Virtual Machine to again communicate to the Ubuntu server via ICMP.
</p>
<br />

<p>
<img src="https://i.imgur.com/FDkGNEv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I then filtered for SSH (port 22) and began establishing an SSH connection to the Ubuntu server, immediately the SSH traffic was shown upon contacting the Ubuntu server to initiate a connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/eqcMXdj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I then filtered for DHCP traffic and renewed the Virtual Machines IP address via a PowerShell command. In doing this I was able to see the request as well as the acknowledgement of the IP address renewal between the Virtual Machine and the DHCP server.
</p>
<br />

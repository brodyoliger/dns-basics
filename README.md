<p align="center">
<img src="https://i.imgur.com/pgYpTCl.png" alt="Traffic Examination"/>
</p>

<h1>Basic configuration of A-records and CNAME records</h1>
In this explanation an Azure Virtual Machine running Microsoft Active Directory will be used to configure A-records and CNAME records and observe the changes. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Windows Virtual Machine)
- Remote Desktop
- Active Directory DNS Manager
- Command line tools

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>High-Level Steps</h2>

- Created the environment for Active Directory to run in
- Opened DNS Manager in Active Directory
- Configured A-records and CNAME records
- Observed the changes caused by these configurations

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/JzbpABX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the Active Directory DNS Manager, I opened the Domain Controllers Forward Lookup Zones to begin customizing records.
</p>
<br />

<p>
<img src="https://i.imgur.com/TFK4FEY.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first example was mapping an A-record, "mainframe" (mainframe.mydomain.com) to the IP address 1.2.0.4(The IP address of the Domain Controller).
</p>
<br />

<p>
<img src="https://i.imgur.com/kkFByWJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upon pinging "mainframe" it showed us that it pinged the IP address of the Domain Controller, the address that the A-record had been set to.
</p>
<br />

<p>
<img src="https://i.imgur.com/RMnn8Uw.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
The next to be configured was the CNAME. For this example I chose "search" to route to "www.google.com".
</p>
<br />

<p>
<img src="https://i.imgur.com/XG5tyMU.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upon pinging "search" in the command line it was clear that the ping was rerouted to "www.google.com".
</p>
<br />

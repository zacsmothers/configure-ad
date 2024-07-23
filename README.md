<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Active Directory
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory on Domain Controller
- Enable Active Directory on Domain Controller
- Configure Users within Active Directory
- Enable User Admin access within Active Directory
- Connect Client Computer to Domain Controller
- Configure Access to Multiple Users within Client Computer
- Use Windows PowerShell ISE to Create Users in Domain Cotroller

<h2>Deployment and Configuration Steps</h2>
<h3>Install Active Directory on Domain Controller</h3>
<p>
<img src="https://i.imgur.com/NQVuAWW.png" height="80%" width="80%" alt="Install Active Directory"/>
</p>
<p>
I Created two Virtual Machines within Microsoft Azure named DC-1 which is the domain controller using the Windows Server 2022 image and another named Client-1 which is the client computer connected to the domain controller using the Windows 10 image. Once the two VMs were set up I installed Microsoft Active Diretcory within the Server Manager on the domain controller.
</p>
<br />
<h3>Enable Active Directory on Domain Controller</h3>
<p>
<img src="https://i.imgur.com/7FRavH3.png" height="80%" width="80%" alt="Enable Active Directory"/>
</p>
<p>
After the installation I continued to set up Active Directory on DC-1 by promoting the server to a domain controller within the Server Manager, then as the picture above shows I clicked
add a new forest to give the domain a name and password.
</p>
<br />
<h3>Configure Users within Active Directory</h3>
<p>
<img src="https://i.imgur.com/p8f2WsI.png" height="80%" width="80%" alt="Config users in AD"/>
</p>
<p>
After the installation completed I launched Active Directory and created two new organizational units named _ADMINS and _EMPLOYEES within the admin organizational unit I created a new user named John Doe which can be seen in the picture above.
</p>
<br />
<h3>Enable User Admin access within Active Directory</h3>
<p>
<img src="https://i.imgur.com/VLBKjyP.png" height="80%" width="80%" alt="Config User to an Admin"/>
</p>
<p>
Although the user was created and placed in the admin organizational unit the account did not have admin access, this was done by enabling "Domain Admins" access in the "Member Of" section within the account "Properties" which can be seen in the picture above.
</p>
<br />
<h3>Connect Client Computer to Domain Controller</h3>
<p>
<img src="https://i.imgur.com/OQo6n5v.png" height="80%" width="80%" alt="Connect Client to DC"/>
</p>
<p>
I then added the Client-1 computer to the domain by first changing the DNS settings of Client-1 to the DC-1 computer's private IP address within the Azure portal then after the two VM's updated I changed the domain for Client-1 within the "Computer Name" section of the "System Properties" inside the Client-1 VM.
</p>
<br />
<h3>Configure Access to Multiple Users within Client Computer</h3>
<p>
<img src="https://i.imgur.com/Za6TGU8.png" height="80%" width="80%" alt="Config access to Multiple Users"/>
</p>
<p>
Then to give multiple users access to Client-1 I first opened the remote desktop settings within Client-1 and within the "Select Users or Groups" field I added Domain Users which gives access to any user within that security group. 
</p>
<br />
<h3>Use Windows PowerShell ISE to Create Users in Domain Cotroller</h3>
<p>
<img src="https://i.imgur.com/wSlXHn7.png" height="80%" width="80%" alt="Use Win PShell ISE to create Users"/>
</p>
<p>
Then to create new users with Windows PowerShell ISE I created a new file with the script seen in the picture above these accounts were then given access to the Domain Users group.
</p>
<br />

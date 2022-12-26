<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Full Video Demonstration</h2>

- ### [How to Deploy on-premises Active Directory within Azure Compute](https://www.flexclip.com/share/18365978708cebdd84a8d073f8908636ffb4982.html)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create VM's in Azure
- Enable connection between VM's in firewall
- Download Active Directory on Domain Control VM
- Join Client VM with Domain Control VM in Azure via DNS
- Set up remote desktop access for non-admins on Client VM

<h2>Abbreviated Deployment and Configuration Steps</h2>

<p>
<img src="https://user-images.githubusercontent.com/47663923/209571749-426ae6fe-5599-4c5a-8d3a-45fdfd44dde0.png" height="80%" width="80%" alt="Create VMs"/>
</p>
<p>
Navigate to Azure portal and create two separate VMs, one as a Windows Server and one as Windows 10. Make sure both are connected on the same network.
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/47663923/209571840-4bb30ce3-cc32-449d-8422-49ecc758b3ca.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On Windows Server VM, navigate to windows firewall and enable all ICMPv4 in inbound rules.
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/47663923/209572013-2932aa36-7227-4b88-b2c2-742b90828f57.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Server Manager, navigate to Add roles and features where you will download/enable Active Directory Domain Services.
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/47663923/209572127-975b729b-1eb7-42a6-ac1d-1325ed871942.png" height="80%" width="80%" alt="Connect VMs using DNS"/>
</p>
<p>
Find Windows Server VM private IP in Azure. Navigate to Windows 10 VM and set DNS server to Windows Server VM IP address too ensure connection to domain.
</p>
<br />

<p>
<img src="https://user-images.githubusercontent.com/47663923/209572488-2006c77d-1e9a-4acb-947c-1a413984bfcb.png" height="80%" width="80%" alt="Connect VMs using DNS"/>
</p>
<p>
While logged into Windows 10 VM as admin, navigate to Remote desktop settings. Select "Select users that can remotely access this PC." Select "add" and type in "domain users." This gives all domain users the ability to log into the VM. 
</p>
<br />

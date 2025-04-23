<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the setup of the pre-requisite Microsoft Azure architecture for Active Directory.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)
  
<h2>High-Level Environment Setup Steps</h2>

- Set up a Domain Controller in Microsoft Azure
- Set up Client-1 in Microsoft Azure
- Checking Connectivity


<h2>Environment Set-Up Steps</h2>

<p>
1) Navigate to <strong>Microsoft Azure</strong> and create a new resource group named <strong>Active-Directory-Lab</strong>.<br />
  <br />
<img src="https://i.imgur.com/RjSeT4B.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>
<br />
<br />
<br />

<p>
2) Create a Virtual Machine named <strong><i>dc-1</i></strong>.  This VM will act as the <strong>Domain Controller</strong> that houses <strong>Active Directory</strong>. <br />
  <br />
<img src="https://i.imgur.com/MqeHx3w.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
  <Strong><i>Note: Ensure the resource group selected is "Active_Directory_Lab"</i></Strong>
</p>
<br />
<br />
<br />
<br />

<p>
3) Ensure the <strong>image</strong> selection reads <strong><i>Windows Server 2022: Azure Edition</i></strong>. <br />
  <br />
<img src="https://i.imgur.com/rTP2V0I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  <strong>Note: This is imperative, ensure dc-1 is running the server version of Windows OS.</strong><br />
</p>
<br />
<br />
<br />
<br />


<p>
4) Next, create a new VM named <strong>Client-1</strong>.<br />
  <br />
<img src="https://i.imgur.com/MEAUWZF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
<strong><i>Note: Ensure <strong>Windows 10 Desktop</strong> runs on client-1. The settings shown above should be applied to client-1.</i></strong>
  
</p>
<br />
<br />
<br />
<br />




<p>
5) Navigate to <strong>Home > Virtual-Machines > dc-1 > Virtual NIC </strong>.<br />
  <br />
<img src="https://i.imgur.com/62diXV5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />


<p>
6) Select <strong>IP Config</strong>. <br />
  <br />
<img src="https://i.imgur.com/sgRgtJ2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
7) Select <strong>Static</strong>. <br />
  <br />
<img src="https://i.imgur.com/FlcFoBj.png" height="60%" width="40%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
8) Navigate to <strong>Home > Virtual Machines > [select dc-1] > Networking Settings > [copy Private I.P Address] </strong>.<br />
  <br />
<img src="https://i.imgur.com/Hjs5ujx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
9) Next, navigate to <strong>Home > Virtual Machines > client 1 | Network Settings > client-1352_z1 </strong>.  Paste the Private IP Address from <strong>dc-1</strong> in the box labeled "DNS Server". <br />
  <br />
<img src="https://i.imgur.com/xzpAYZo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
 
</p>
<br />
<br />
<br />
<br />

<p>
  10) Finally, log in to <strong>client-1</strong>; Open <strong>powershell</strong> and ping <strong>dc-1</strong> to ensure the process has worked. <br />
  <br />
<img src="https://i.imgur.com/OkGW9Un.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />




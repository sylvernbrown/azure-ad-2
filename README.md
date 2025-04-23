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
1) Log into <strong>dc-1</strong> and select <strong>"Add Roles and Features"</strong>.<br />
  <br />
<img src="https://i.imgur.com/yQpm7IK.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>
<br />
<br />
<br />

<p>
2) To install Active Directory Domain Services, navigate to <strong>Server Roles > Active Directory Domain Services</strong>.<br />
  <br />
<img src="https://i.imgur.com/7goyu1N.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
  <Strong><i>Note: Ensure the resource group selected is "Active_Directory_Lab"</i></Strong>
</p>
<br />
<br />
<br />
<br />

<p>
3) Click on the flag with the orange triangle and <strong>"Promote this server to a new domain controller"</strong>. <br />
  <br />
<img src="https://i.imgur.com/f7C8uzQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  <strong>Note: This is imperative, ensure dc-1 is running the server version of Windows OS.</strong><br />
</p>
<br />
<br />
<br />
<br />


<p>
4) Next, navigate to <strong>Deployment Configuration > Add a New Forest > mydomain.com (or any alternative domain name) </strong>.<br />
  <br />
<img src="https://i.imgur.com/LxKMBBl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
<strong><i>Note: Ensure <strong>Windows 10 Desktop</strong> runs on client-1. The settings shown above should be applied to client-1.</i></strong>
  
</p>
<br />
<br />
<br />
<br />




<p>
5) Since we are logged on locally to dc-1, log out and re-login using the new domain name information as seen below.<br />
  <br />
<img src="https://i.imgur.com/53IgUIW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />


<p>
6) Now we are going to create an employees organizational unit in <strong>Active Directory Users and Computers (ADUC)</strong>. Navigate to <strong>search</strong> and enter <strong>Active Directory Users and Computers</strong>. [Right click] <strong>mydomain.com > New > Organizational Unit </strong> <br />
  <br />
<img src="https://i.imgur.com/ksyL5Qj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
7) Name the Organizational Unit <strong>"_EMPLOYEES"</strong>. <br />
  <br />
<img src="https://i.imgur.com/PBGXTKW.png" height="60%" width="40%" alt="Disk Sanitization Steps"/> <br />
  <strong><i>Note: It's crucial the name _EMPLOYEES is entered verbatim or else later steps will not work.</i></strong>
  
</p>
<br />
<br />
<br />
<br />

<p>
8) Add another Organizational Unit named <strong>"_ADMINS"</strong>.<br />
  <br />
<img src="https://i.imgur.com/8slDvvw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
9) Now, we will add a user to the "_ADMINS" Organizational Unit. Navigate to <strong>Active Directory Users and Computers > [right click] _ADMINS (under mydomain.com) > New > User. </strong> <br />
  <br />
<img src="https://i.imgur.com/F6ztp6l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
 
</p>
<br />
<br />
<br />
<br />

<p>
  10) For demonstration purposes, the user is named Jane Doe.  However, the specific name is less important; just any username that can be easily remembered for testing purposes will do.  However, be sure to note the username and password for login purposes later on. <br />
  <br />
<img src="https://i.imgur.com/G4MblJ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
11) Once "Jane Doe" is added as a user in the "_Admins" OU, [right click] Jane Doe > [select] Properties.<br />
  <br />
<img src="https://i.imgur.com/pVeRDwq.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
</p>
<br />
<br />
<br />

<p>
12) In the properties section of Jane Doe, select "member of" and select "Add".  A text box will appear, type "Domain Admins".  This will grant Admin permissions to Jane Doe, the Organizational Unit alone will not do this automatically. <br />
  <br />
<img src="https://i.imgur.com/2HmXThg.png" height="60%" width="80%" alt="Disk Sanitization Steps"/><br />
  <Strong><i>Note: Ensure the resource group selected is "Active_Directory_Lab"</i></Strong>
</p>
<br />
<br />
<br />
<br />

<p>
13) Now, disconnect from dc-1 to logon using our updated "Jane Doe" user. <br />
  <br />
<img src="https://i.imgur.com/oeywsHB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  <strong>Note: This is imperative, ensure dc-1 is running the server version of Windows OS.</strong><br />
</p>
<br />
<br />
<br />
<br />


<p>
14) Now, log into dc-1 using the following information.<br />
  <br />
  <strong>Username:</strong>mydomain.com\[username] <br />
  <strong>Password:</strong>[password]
  <br />
<img src="https://i.imgur.com/i2VnmpL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
<strong><i>Note: Ensure <strong>Windows 10 Desktop</strong> runs on client-1. The settings shown above should be applied to client-1.</i></strong>
  
</p>
<br />
<br />
<br />
<br />




<p>
15) Now, we are going to join Client-1 to our newly-created domain. Navigate to <strong> Settings > About > Rename this PC (Advanced)</strong><br />
  <br />
<img src="https://i.imgur.com/rafTcaK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />


<p>
16) Under <strong>"Member Of"</strong> select <strong>"Domain"</strong> and enter <strong>"mydomain.com"</strong>. <br />
  <br />
<img src="https://i.imgur.com/5EBhFMO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
17) Once completed, a prompt will ask for admin verification. Enter the adminuser you created in the previous steps to join Client-1 to the domain. <br />
  <br />
<img src="https://i.imgur.com/1KPHc7G.png" height="60%" width="40%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
18) For changes to be implemented, a restart will be required. Click <strong>"Restart Now"</strong>.<br />
  <br />
<img src="https://i.imgur.com/viTuBws.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />

<p>
19) Next, we are going to create another Organizational Unit Navigate to <strong>Active Directory Users and Computers</strong>.<br />
  <br />
<img src="https://i.imgur.com/x1KjUDR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
 
</p>
<br />
<br />
<br />
<br />

<p>
20) <strong>[Right Click] mydomain.com > New > Organizational Unit</strong>. <br />
  <br />
<img src="https://i.imgur.com/HyeqUMH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
 
</p>
<br />
<br />
<br />
<br />

<p>
  21) Name the Organizational Unit <strong>_CLIENTS</strong>. <br />
  <br />
<img src="https://i.imgur.com/3eFc5sQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
  
</p>
<br />
<br />
<br />
<br />




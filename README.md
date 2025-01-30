<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>😊

- Domain Controller VM (Windows Server 2022) named “DC-1”
- Domain Controller’s NIC Private IP address to be static
- ICMPv4 (ping) was allowed on the Domain Controller
- Create an Admin and Normal User Account in Active Directory
- Join Client to domain
- Attempt to login Client-1 with one of the users

<h2>Deployment and Configuration Steps</h2> 🚀

- First step is creating the resource group in which you can see below the name as Active-directory. We will create both virtual machines (Dc-1) and (Client-1) with the same resource group. Dc-1 will use the (Windows server 2022 system) and the Client-1 virtual machine will use the Windows 10 pro system image (another version of the entire system). Both virtual machines will also be under the same virtual network named (active-directory-vnet).

<p>
<img src="https://i.imgur.com/lftxE3Q.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/hCpD5bi.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

- We see the virtual machine (Client-1) created with the same Resource group and Vnet once again. 
<p>
<img src="https://i.imgur.com/z1ppYcy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/PRtApxp.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

- Now we need to make sure the IP address of Dc-1 switches from dynamic to static in order to maintain the connection to the private IP address.
<p>
<img src="https://i.imgur.com/9aOOrWA.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

- Next we must eventually connect the Client VM (Client-1) to the Domain controller and thus it is important to change the DNS servers on Client-1 to the private IP address of DC-1 (10.0.0.4) which is pictured below.
- We will select the NIC on client-1 to change the DNS to the private IP address of DC-1.

<p>
<img src="https://i.imgur.com/3rkXIzU.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
</p>
<br />

- We will now go into Client-1 VM and attempt to ping DC-1 to esatblish the connection👍
- ICMPv4 (ping) was allowed on the Domain Controller's (DC-1) Firewall in Windows Firewall
- We log into Client-1 through Remote Desktop Connection (RDP)
- Let's use Powershell and type into the command line ping (10.0.0.4), which is the private IP address of DC-1. Once you recieve the reply from the private IP it was successful. 😊

<p>
<img src="https://i.imgur.com/AjdrBIa.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>

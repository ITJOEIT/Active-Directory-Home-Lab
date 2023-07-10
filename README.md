<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
In this project I created my own Active Directory lab using VirtualBox. The lab makes use of two virtual machines, one a Server, the other a Client. The Server, acting as a Domain Controller housed Active Directory. The following shows a simple guide for the creation of this lab.
<br />


<h2>Environments and Languages Used</h2>

- <b>VirtualBox</b>
- <b>Windows Server</b>
- <b>Windows 10</b>
- <b>PowerShell</b> 

<h2>Project walk-through:</h2>

<p align="center">
Active Directory Diagram illustrating the infrastructure of the lab: <br/>
<br />
<img src="https://i.ibb.co/3dSwSVK/Image0.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
Firstly, I configured a Virtual Machine as a Domain Controller: <br/>
<br />
<img src="https://i.ibb.co/n0bkb2Y/Image1.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
This Domain Controller will have two NICs, one facing the Internet and one internal:  <br/>
<br />
<img src="https://i.ibb.co/c2dhQbh/Image2.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
I then installed Active Directory Domain Services: <br/>
<br />
<img src="https://i.ibb.co/YTF51BG/Image3.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
I added a new forest and renamed it mydomain.com:  <br/>
<br />
<img src="https://i.ibb.co/Bj15BWT/Image4.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
After restarting the virtual machine, mydomain\Administrator was shown:  <br/>
<br />
<img src="https://i.ibb.co/19nQB3J/Image5a.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
Next I created a dedicated domain administrator account:  <br/>
<br />
<img src="https://i.ibb.co/JRwYdKL/Image6.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
Then I created a remote access server/network address translation. This will allow our Windows 10 client to be on the private virtual network, while giving them the ability to connect to the Internet through the Domain Controller:  <br/>
<br />
<img src="https://i.ibb.co/qWfwkpn/Image7.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<img src="https://i.ibb.co/ft0f5KP/Image8.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
Next I created a DHCP server with enough available IP addresses to be used for this test lab.:  <br/>
<br />
<img src="https://i.ibb.co/6shqskP/Image9.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
I used a PowerShell script to automatically create users for the Active Directory lab:  <br/>
<br />
<img src="https://i.ibb.co/6JZGqvM/Image10.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
 <br />
I then created another virtual machine that acted as a Windows 10 client:  <br/>
<br />
<img src="https://i.ibb.co/CbVKSL8/Image11.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
 <br />
I checked to see ifI could ping the domain controller:  <br/>
<br />
<img src="https://i.ibb.co/cyt3KxQ/Image12.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
 <br />
Back at the DHCP server, I saw there had been a request from the client for an address, which had been granted and a lease has been sent:  <br/>
<br />
<img src="https://i.ibb.co/LdrXHWh/Image13.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
 <br />
Also, the client was now a member of the domain, confirming that the lab was fully functional:  <br/>
<br />
<img src="https://i.ibb.co/mBcdvjX/Image14.png" height="50%" width="50%" alt="Active Directory Lab"/>
<br />
<br />
 Thank you for reading this project.
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

# Joining-a-computer-to-an-Active-Directory-server

<h2>Description</h2>
This SOP will demenstrate how to add a computer to an Active Directory server
<br/>


<h2>Utilities Used</h2
                                 
- <b>Microsoft Azure</b>
- <b>Remmina (RDP client)</b>
- <b>Windows Server 2025</b>
- <b>Windows 11 Pro

<h2>Key Steps:</h2>

**1. Create a Second Virtual Machine**

 - <b> In Azure, create a new virtual machine</b>
 - <b> Chose the same region and availabilty zone as the Active Directory server</b>
 - <b> Select Windows 11 Pro x64 for the image</b>
 - <b> For disk, keep everything as default</b>
 - <b> Under networking, select the virtual network and subnet associated with the Active Directory server</b>
 - <b> Deploy machine</b>

 **2. Congfigure Client's Internet Adapter**

 - <b> Open the command line on both the Windows client and Server by typing cmd into the search bar.  Use the command ipconfig</b>
 - <b> On the Windows Client, right click on the network icon to open network and internet settings</b>
 - <b> Under Ethernet, select edit more adapter settings</b>
 - <b> In ethernet properties, select Internet Protocol Version 4</b>
 - <b> Click use the follow IP address.  Set the IP address to the address given from the ipconfig command from the client (172.16.0.6).  Subnet mask will be 255.255.255.0.  The default gateway will also be from the ipconfig command of the client (172.16.0.1)</b>
 -  <b> Select use the following DNS server addresses.  Preferred DNS server will be the result of the Server ipconfig (172.16.0.4).  For the alternate DNS server use Google's DNS (8.8.8.8)</b>

 **3. Join the Client to the Workstation**

 - <b> Right click the Windows Icon and select System</b>
 - <b> Under Related links click on Domain or workgroup</b>
 - <b> Under the Computer Name tab select Change to rename the Client's name and add it to the domain</b>
 - <b> Change the computer name to Workstation1-East.  Select the client to be a member of mydomain.com</b>
 - <b> Windows Security will then prompt for a user name and password.  It will be the same as the Windows Server
 - <b> A notification will say the client has successfully joined the domain</b>

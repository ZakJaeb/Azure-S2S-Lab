<h1>Azure S2S VPN Tunnel to Homelab</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
In this project I configured an IPSec connection from my Azure tenant to my homelab environment. After successful configuration I was able to RDP into an Azure VM using its private 10.0 IP. I then performed a ping request back to the machine in my home environment using its private 192.168 IP. 

Within Azure I deployed a Virtual Network with two subnets, one for the Gateway and another for the VM. I setup a Virtual Network Gateway with a Public IP to route traffic over the S2S tunnel. I configured a Local Network Gateway to represent my homelab network and setup the VPN connection with Shared key.

For my on-premise gateway I used a TP-Link ER605 Gigabit VPN Router. I also used a TP-Link access point to connect my Macbook Air to the internal network. I configured the IPsec tunnel on my TP-Link router by providing the Azure Public IP and Shared Key.

After verifying that the tunnel was enabled and operational, I used Microsoft Remote Desktop to RDP into a Windows Server 2022 VM I had setup earlier. To test further, I pinged my Macbook from the Windows Server VM.

This project was a great way to learn all about configuring simple networks in Azure and how an enterprise might use a very similar approach for a hybrid cloud environment.
<br />


<h2>Platforms and Technology Used</h2>

- <b>Azure Virtual Networks</b> 
- <b>Azure Virtual Machines</b>
- <b>Azure Network Gateways</b>
- <b>TP-Link Gigabit VPN Router</b>

<h2>Environments Used </h2>

- <b>Azure Portal</b>

<h2>Project walk-through:</h2>
<!--
<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

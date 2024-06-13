<h1>Azure S2S VPN Tunnel to Homelab</h1>

<!-- ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo) -->

<h2>Description</h2>
In this project I configured an IPSec connection from my Azure tenant to my homelab environment. After successful configuration I was able to RDP into an Azure VM using its private 10.0 IP. I then performed a ping request back to the machine in my home environment using its private 192.168 IP. 
<br />
<br />
Within Azure I deployed a Virtual Network with two subnets, one for the Gateway and another for the VM. I setup a Virtual Network Gateway with a Public IP to route traffic over the S2S tunnel. I configured a Local Network Gateway to represent my homelab network and setup the VPN connection with Shared key.
<br />
<br />
For my on-premise gateway I used a TP-Link ER605 Gigabit VPN Router. I also used a TP-Link access point to connect my Macbook Air to the internal network. I configured the IPsec tunnel on my TP-Link router by providing the Azure Public IP and Shared Key.
<br />
<br />
After verifying that the tunnel was enabled and operational, I used Microsoft Remote Desktop to RDP into a Windows Server 2022 VM I had setup earlier. To test further, I pinged my Macbook from the Windows Server VM.
<br />
<br />
This project was a great way to learn all about configuring simple networks in Azure and how an enterprise might use a very similar approach for a hybrid cloud environment.
<br />
<br />
Network Diagram:  <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/a9d51944-f5f2-4681-b719-62cd240dedbe" height="80%" width="80%" alt="Azure S2S Network Diagram"/>

<h2>Platforms and Technology Used</h2>

- <b>Azure Virtual Networks</b> 
- <b>Azure Virtual Machines</b>
- <b>Azure Network Gateways</b>
- <b>TP-Link Gigabit VPN Router</b>

<h2>Environments Used </h2>

- <b>Azure Portal</b>

<h2>Project walk-through:</h2>

<p align="center">
Setup Azure Resource group: <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/054f9f19-86ad-454c-8d9f-788169bba40a" height="80%" width="80%" alt="Azure Resource Group"/>
<br />
<br />
Configure Virtual Network and Subnets: <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/b3a6d150-1a6f-44f4-9611-a15c9cd987af" height="80%" width="80%" alt="Virtual Network"/>
<br />
<br />
Setup Virtual Network Gateway and Local Network Gateway: <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/e13b738b-c1c8-4fb7-98ce-f13325d2c91b" height="80%" width="80%" alt="Virtual Network Gateway"/>
<br />
<br />
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/c27a1a29-5b72-4161-bd59-6067845352e5" height="80%" width="80%" alt="Local Network Gateway"/>
<br />
<br />
Configure IPSec VPN Tunnel in TP-Link Router:  <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/cd2b76ca-b1d9-489f-b47b-7d6a63e1f2e5" height="80%" width="80%" alt="IPSec VPN Tunnel"/>
<br />
<br />
Create Lab VM running Windows Server 2022:  <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/a8289d7a-5a14-49df-aa29-6191df4d92d5" height="80%" width="80%" alt="Lab VM"/>
<br />
<br />
RDP into VM using private IP:  <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/2f03ffdb-b282-407d-8940-199978583a7e" height="80%" width="80%" alt="RDP"/>
<br />
<br />
Ping back to machine on local network:  <br/>
<img src="https://github.com/ZakJaeb/Azure-S2S-Lab/assets/58833790/05f41a8b-8c39-48df-99d0-2a362f7817d5" height="80%" width="80%" alt="Ping"/>
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

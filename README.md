<p align="center">

  ![548CB858-419A-4165-92F5-9FBCEA8DFB81](https://github.com/user-attachments/assets/870b1a11-dc8a-4441-80c4-e778d3bf74ae)

</p>

<h1> Troubleshooting and Firewall Deployment Using (NSG's)</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)
- Powershell

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Virtual Machines
- Test Connectivity 
- Observe imcp Traffic 
- Configure firewall (NSG)
- Observe 

<h2>Actions and Observations</h2>

<p>
<img width="1710" alt="C3BBF88D-1864-42AA-AFE6-B6A842D93B7E" src="https://github.com/user-attachments/assets/b24b1573-9777-46f4-8fbb-c816120ed92c" />
</p>
<p>
To kick of the lab I created 2 Virtual Machines; 1 (Windows) and the other (Linux). To allow them to communicate with eachothe I also placed them on the samae virtual network and withing the same resource group. 
</p>
<br />

<p>
<img width="1653" alt="81AEF063-D3A2-4153-B240-E8E48525EE8D" src="https://github.com/user-attachments/assets/79cf2434-7ff2-4247-bfa3-aaf462d1b5d6" />
</p>
<p>
I tested the connection to the (Linux) Virtual Machine using (ping) command + the private ip address. There is a response from the other virtual machine and traffic between the VM's inside can be observed in (Wireshark) by filtering for icmp traffic.
</p>
<br />

<p>
<img width="1710" alt="FA49A270-0B69-432A-A671-695D35806160" src="https://github.com/user-attachments/assets/bce162ee-0809-4521-a66d-f3176e29857e" />
</p>
<img width="1704" alt="70E7AC49-BBD4-4E31-B63E-B224171AF58D" src="https://github.com/user-attachments/assets/0cf2321f-7544-41fb-827c-5ef324574828" />
<p>
To configure a firewall I went into the Lenox virtual machine/Nwtwork settings/Network security group/Inbound security rules/Add a rule and configured the rule to deny ICMP4 traffic. 
</p> 
<br />

<p>
<img width="1657" alt="5AEBAC7E-57A1-4090-BF34-0709F44DC942" src="https://github.com/user-attachments/assets/45dd8adc-a7c4-49e6-bbe2-50e6cf8a66d8" />
</p>
<p>
Previously a perpetual ping was started to observe the virtual machines commuicating with eachother using the command (ping -t) and now we can see request time outs because of the aforementioned firewall
</p>
<br />

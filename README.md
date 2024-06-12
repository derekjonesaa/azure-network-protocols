<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04


<h2>Actions and Observations</h2>

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/f3e6f991-d58f-4381-b421-cafa6792d9a1)
Step 1: Create two Vitrual Machines in Azure: Log into the Microsoft Azure Portal with your Microsoft Account --> search "resource groups" in the search bar --> "create" resource group --> search "Virtual Machines" in the search bar --> "create" two Virtual Machines with the following OS: Windows 10 OS for VM1 & Ubuntu OS for VM2) --> Make sure both VMs are in the same "resource group". *When setting up the VMs remember the username and password that you use. You'll need this information later to remote desktop into the VMs. I recommend using the same login information for both VMs.




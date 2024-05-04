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

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Setting up an Azure virtual network involves the following steps:

Sign in to the Azure Portal: Access the Azure Portal using your Azure account credentials.

Create a Virtual Network (VNet): Search for "Virtual Networks" in the search bar and select "Virtual Networks" from the search results. Click on "Add" to create a new VNet.

Define VNet settings: Give your VNet a name and choose the subscription, resource group, and location. Specify the address space for the VNet, which defines the IP address range. You can also configure DNS server settings if necessary.

Configure subnets: Within the VNet, create one or more subnets. Define the subnet name and IP address range for each subnet. Ensure that the subnet ranges do not overlap.

Advanced networking options: You may choose to configure additional settings, such as Network Security Groups (NSG) for controlling inbound/outbound traffic, User-Defined Routes (UDR) for custom routing, and VPN Gateway for connecting on-premises networks.

Peer virtual networks (optional): If you have multiple VNets and want to enable communication between them, you can set up VNet peering. This allows network traffic between the peered VNets.

Set up network security: Configure NSGs to enforce network security rules for subnets and control inbound/outbound traffic. You can define rules for allowing or denying specific protocols and port access.

Associate resources: Associate resources like virtual machines (VMs), load balancers, and other services with the virtual network. Ensure that the resources are deployed within the desired subnets.

Test connectivity: Validate connectivity by testing communication between resources within the virtual network. Verify that the configured network settings are functioning as expected.

By following these steps, you can easily set up a virtual network in Azure, which provides a secure and isolated network environment for your applications and services, enabling seamless communication and connectivity.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

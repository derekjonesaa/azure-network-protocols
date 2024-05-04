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


![image](https://github.com/derekjonesaa/configure-ad/assets/167825508/337595dc-a39e-42f6-a016-5160b7ed099c)

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


![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/9b88c9ed-93ef-4336-9eed-94573f370ee7)


</p>
To ping an IP address, follow these steps:

1. Open the command prompt: On Windows, press the Windows key, type "cmd," and press Enter. On macOS, open the Terminal application. On Linux, open the Terminal or use the Ctrl+Alt+T shortcut.

2. Type the ping command: In the command prompt or Terminal, type "ping" followed by a space and then the IP address or hostname you want to ping. For example, "ping 192.168.1.1" or "ping www.example.com".

3. Initiate the ping: Press Enter to run the ping command. The system will start sending ICMP (Internet Control Message Protocol) echo request packets to the specified IP address or hostname.

4. Observe the ping results: The ping command will send several packets to the target IP address or hostname, and you will see the response for each packet in the command prompt or Terminal. It will display details such as the round-trip time (RTT), indicating how long it takes for the packet to reach the destination and return.

5. Analyze the ping statistics: Look for information such as the average RTT, packet loss percentage, and any indications of network issues. A successful ping will show low RTT values and no packet loss. High packet loss or unusually long response times may suggest network problems.

6. Interpret the results: If you receive responses from the target IP address or hostname, it means the connection is successful. If the ping fails or times out, it suggests that the target IP address or hostname is not reachable or that there might be a network connectivity issue.

Some network setups or firewalls may block or prioritize ICMP traffic, which could result in inconsistent or no ping responses. In such cases, consider using other network troubleshooting tools or checking with your network administrator.


<br />

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/40197c8d-1eb1-4c7f-baa8-fd2410360ca8)

To use Wireshark follow these steps:

1. Install Wireshark: Download and install Wireshark from the official website (www.wireshark.org) compatible with your operating system.

2. Launch Wireshark: Once installed, open Wireshark on your computer.

3. Select a Network Interface: In the Wireshark interface, select the network interface you want to capture packets from. It could be Ethernet, Wi-Fi, or any other available interface.

4. Start Capturing Packets: Click on the "Start" or "Capture" button to begin capturing network traffic on the selected interface.

5. Analyze Packets: As packets are captured, you will see a live stream of network traffic in the Wireshark window. The captured packets will display various details like source and destination IP addresses, protocols, packet size, and more. You can filter and sort packets based on specific criteria.

6. Filter Results: Use Wireshark's display filters to narrow down and focus on specific packets of interest. Filters can be set by protocol, source or destination IP address, port number, or other criteria.

7. Analyze Packet Details: Click on individual packets in the Wireshark window to view detailed information about the packet, including protocol headers, payload data, and any errors or anomalies.

8. Follow Streams and Conversation Analysis: Wireshark allows you to follow and analyze individual conversations or streams between specific source and destination IP addresses. This can be useful for identifying patterns or troubleshooting network issues.

9. Save and Export Captured Data: You can save the captured packet data in various formats, including pcap (Wireshark's default format), CSV, or plain text. Exporting the data allows you to share it for further analysis or review.

10. Stop Capturing: Once you have captured enough data or completed your analysis, click on the "Stop" or "Capture" button to stop capturing packets.



<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)
- PowerShell (Command-Line lnterface)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

High-Level Steps

Step 1: Create Virtual Machines

Step 2: Remote Desktop into VMs

Step 3: Install & Run WireShark

Step 4: Test Connectivity Between VMs

Step 5: Alter Network Security Group Settings

Step 6: SSH into VM

Step 7: Observe DHCP Traffic

<h2>Actions and Observations</h2>

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/f3e6f991-d58f-4381-b421-cafa6792d9a1)
Step 1: Create two Vitrual Machines in Azure: Log into the Microsoft Azure Portal with your Microsoft Account --> search "resource groups" in the search bar --> "create" resource group --> search "Virtual Machines" in the search bar --> "create" two Virtual Machines with the following OS: Windows 10 OS for VM1 & Ubuntu OS for VM2) --> Make sure both VMs are in the same "resource group". *When setting up the VMs remember the username and password that you use. You'll need this information later to remote desktop into the VMs. I recommend using the same login information for both VMs.

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/893878b4-b9ba-4553-9b62-073e8a650d85)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/22b054cc-0092-43a4-8343-d198ec1c4ab9)

Step 2: Remote Desktop into each "Virtual Machine". Go to --> VM1 settings --> copy "public IP address" --> search "remote desktop connections" in start menu search bar --> Open "Remote Desktop Connection" & paste copied IP address from VM1 --> click connect --> Use the Username & Password created in step 1 to sign in to the VM. Repeat the same steps to log into VM2.

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/08b0bc8a-0eba-4726-9878-e6994d8a8c7f)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/46bfc651-685a-4e42-bf39-bc6f04502def)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/93e18a11-f84a-4447-9daa-c5acade2dc24)
Step 3: While into VM1, download WireShark. Search "WireShark" on google --> click Wireshark's official site --> "Windows Installer (64-bit)" download --> Install WireShark and go through installation prompts --> Open WireShark --> click "Ethernet 2" --> next select "shark symbol" in upper left hand corner to start network traffic monitoring --> Filter out irrelevant network traffic via display filter bar (type "icmp" in filter bar to only see ping traffic).

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/149640dd-f95a-4641-a580-38d044a0d293)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/41cce259-0f88-46d9-856e-676ea4342a85)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/a7dd37fd-4956-42b4-a00c-4a9d94328ee1)
Step 4: Go to VM2 on Azure Portal --> "overview" --> copy the "private IP address" --> Go to VM1 --> Search "PowerShell" in the start menu search bar & open it --> Type "ping -t" then paste VM2's private IP address into "PowerShell" to start a "perpetual ping" (WireShark will now show the two VMs pinging back and forth, allow the ping to continue). Pay attention to all of the data being communicated between both VMs on this step

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/303d45c0-4130-42f6-9796-5f3855a9c238)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/a425dd4e-09f6-4e54-ae03-1170ee992581)
Step 5: Go back to Azure Portal --> type "Network Security Group" in the search bar (this is the VMs firewall) --> select "VM2-NSG" --> "Inbound security rules" under settings --> click "+ add" --> in the new pop up window change "protocol" to "ICMP" --> change "action" to "deny" --> change "Name" to "Deny_ICMP_Ping" --> Click "add" at bottom. *Notice how the ping cmd in PowerShell on VM1 done on step#4 is immediately halted due to being blocked by VM2's firewall thanks to the new inbound security rule you made. If you edit the rule to allow traffic, notice how the perpetual ping cmds successfully resume. *Press Ctrl+C to stop PowerShell ping

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/2b5fb868-8e80-4623-bc65-465f95acc86f)
![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/c594c451-b8f2-4790-b364-df299f6651ee)
Step 6: SSH into VM2 from VM1 via PowerShell. Type "SSH" into WireShark's filter bar (reference step 3) --> Go to "PowerShell" again, type "ssh labuser@(VM1 private IP address)" into the cmd line *view screenshot above for help --> Type "yes" to connection prompt --> enter password on next cmd line (password will not show but enter it anyway and press enter key, it will register) --> You have now successfully remotely logged into VM2's command-line Interface (CLI). It should now read "labuser@VM2:". You can type a linux cmd such as: "id" to see the new network traffic between the VMs since linking via SSH. When finished exploring, type "exit" into cmd line on PowerShell to end the connection.

![image](https://github.com/derekjonesaa/azure-network-protocols/assets/167825508/d31c7931-cac3-4f60-996c-ad87a9ab542d)
Step 7: Next you will observe DHCP traffic the same as you did with SSH. Type "DHCP" into WireShark's filter bar (reference step 3) --> Go to "PowerShell" again, type "ipconfig /renew" into the cmd line to request a new IP address for VM1 from the Azure DHCP server (you may lose connection to the VM, if so, just RDH back into it) --> You should see the newly issued IP address in WireShark. That concludes this lab.

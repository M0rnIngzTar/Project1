<h1>Networking Implementations</h1>

<h2>Introduction</h2>
 I was tasked with creating a network infrastructure for a multinational organisation with locations in two major cities: London and Paris. The objective was to design a network topology that enables seamless connectivity between these two sites, allowing users in both locations to share resources and collaborate efficiently.
I have successfully implemented this network and clearly defined the project’s scope. This report will provide comprehensive evidence of the network’s development, demonstrating how the implementation phase aligns with the initial design and fully meets the project’s requirements. Additionally, the report will cover the configurations, deployment strategies, and integration of key technologies, including computer systems, digital networks, and cybersecurity protocols. This ensures a secure, efficient, and scalable network solution capable of supporting the organisation’s multinational operations.
<br />

<h2>The Approach</h2>
To build and deploy the network, I have utilized Microsoft Azure to create a virtual network (VNet) and virtual machines (VMs). With the advice of my manager, I have chosen to build and deploy the network using cloud infrastructure to leverage scalability, flexibility, and enhanced security features. This ensures a modern and robust solution that aligns with industry best practices.
<br />

<h2>Resource Group</h2>
The process began by creating a resource group in Microsoft Azure to organise and manage the components of the network. The resource group can be viewed as a container that holds related resources, as illustrated in Diagram 1. As shown, the resource group created for this project is named MicahResourcesGroup. This is where the core components of the network were built, including the creation Virtual Networks (VNets), Virtual Machines (VMs) and the configuration of the network gateway. 
<br />

<p align="center">
Diagram 1: <br/>
<img src="https://imgur.com/bEAaLtn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
  
<h2>Virtual Networks</h2>
After creating the resource group, I successfully implemented the network by creating two Virtual Networks (VNETs) in Azure, one for each city, to support secure communication and resource sharing. Each VNET  is configured with its own IP address space to ensure no overlap and smooth inter-network routing.
<br />

<p align="center">
Diagram 2: <br/>
<img src="https://imgur.com/Fsj3t6B.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 

<p align="center">
Diagram 3: <br/>
<img src="https://imgur.com/sgJqyZH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 

<p align="center">
Diagram 4: <br/>
<img src="https://imgur.com/AowXbWw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 

<p align="center">
Diagram 5: <br/>
<img src="https://imgur.com/5hhWWzs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
Diagrams 2 and 5 clearly demonstrate the successful completion and implementation of this process.
<br />
<h2>Subnetwork</h2>
To effectively organise and optimise network performance, as well as manage IP addresses efficiently, subnets are created. This enables the virtual network that I created to be divided into smaller, more manageable segments, improving both control and efficiency. This was set up for various purposes like FTP server, web server, PCs, and Wireless machines.  
<br />

<p align="center">
Diagram 6: <br/>
<img src="https://imgur.com/SzoWykb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
As depicted in Diagram 6, the London VNET has been meticulously designed to accommodate various network segments by allocating specific subnets, each with its own unique IP range which goes the same for Paris VNET as shown in Diagram 7.
Additionally, in the LondonVNET, I created two separate subnets for PCs, each designed to simulate a logical separation, much like a VLAN (Virtual Local Area Network). By implementing PCSubnet and PCSubnet2, I effectively segmented network traffic between groups of devices, ensuring enhanced security and better traffic management. This logical separation mimics VLAN behaviour, where different departments or device groups within an organisation can communicate within their segment but are isolated from others, promoting security and network efficiency.
<br />
<p align="center">
Diagram 7: <br/>
<img src="https://imgur.com/yubrrDi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
Each subnet within the London VNET and Paris VNET has been carefully allocated a dedicated range of IP addresses to support specific roles and network functions. These subnets will later be used to deploy Virtual Machines (VMs), ensuring that each machine is assigned to the correct network segment based on its function.
<br />
<h2>Gateways and Gateways connection</h2>h2>
To ensure secure communication between the London and Paris VNETs, Virtual Network Gateways were strategically deployed. These gateways facilitate encrypted VPN connectivity, effectively simulating a VNET-to-VNET connection between the two locations. Enabling both sites to communicate as if they were part of a unified network while maintaining strong security protocols across Azure's infrastructure as shown in Diagram 8 and 9.
<br />
<p align="center">
Diagram 8: <br/>
<img src="https://imgur.com/QDnHB01.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
<p align="center">
Diagram 9: <br/>
<img src="https://imgur.com/CViqC8h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
After the gateways were deployed, VNET Peering was established between London VNET and Paris VNET. A VPN connection was configured between the two virtual gateways to enable secure, encrypted communication between London and Paris.
<br /> 
<h2>Virtual Machines</h2>
The Virtual Machines (VMs) were created using Azure. In this network setup, all servers have been configured to allow Remote Desktop Protocol (RDP) access via port 3389 which is only recommended for testing. This allows authorized administrators and users to remotely connect to the servers. While RDP access is essential for remote management, NSGs are configured to allow RDP access only from specific, trusted IP ranges, preventing unauthorized access.
Diagram 10 to 13 is a break down to show a clearer understanding of the function and role of each virtual machine within the network set up. 
<br />
<p align="center">
Diagram 10: <br/>
<img src="https://imgur.com/7tHIoLT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
The FTP server for the London network, responsible for handling file transfers for employees in the London office. It allows file uploads and downloads.
<br />
<br /> 
<p align="center">
Diagram 11: <br/>
<img src="https://imgur.com/KET1bZb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
A virtual PC instance for a London-based employee. This virtual machine is part of the employee subnet and is used for day-to-day tasks such as accessing network resources and performing administrative work
</b>
<p align="center">
Diagram 12: <br/>
<img src="https://imgur.com/X9Zdnlr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
This virtual machine is designated as the web server for the London network. It hosts web applications and is accessible by internal users from both London and Paris through the VNET-to-VNET connection
</b>
<p align="center">
Diagram 13: <br/>
<img src="https://imgur.com/e1WkuEy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
This virtual machine is configured as the FTP server for the Paris office, handling file-sharing operations for Paris-based employees.
</b>
<p align="center">
Diagram 14: <br/>
<img src="https://imgur.com/ngwbrvt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
A virtual PC instance for an employee based in the Paris office. This VM simulates a workstation used for daily tasks, such as accessing shared network resources and company systems.
These VMs are crucial for supporting services such as web hosting, file transfer and ensuring smooth operations between the London and Paris. 
<br />
<h2>Testing</h2>
After the deployment, thorough testing was conducted to ensure all network requirements were met:
<h3>Ping Test</h3>
London to Paris: Diagram 15 shows that London (MicahLDNPC1) successfully pinged Paris (MicahParisPC1) confirming  cross-site connectivity via the gateway connection.
<br />
<p align="center">
Diagram 15: <br/>
<img src="https://imgur.com/Nx7L57h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
Paris to London: Similarly, Paris (MicahParisPC1) was able to successfully ping London web server (MicahLDNWebServer) as shown in Diagram 16.
<p align="center">
Diagram 16: <br/>
<img src="https://imgur.com/f9WQPpu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
<h3>Web Server Access Test</h3>
London (MicahLDNPC1) and Paris (MicahParisPC1) PCs could both access the London web server by navigating to http://10.10.1.4 as shown in Diagram 17. 
<br />
<p align="center">
Diagram 17.1: <br/>
<img src="https://imgur.com/6Tud1UK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
<p align="center">
Diagram 17.2: <br/>
<img src="https://imgur.com/vXTPp4M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
<h3>FTP Server Access Test</h3>
London FTP Access: MicahLDNPC1 could access the FTP server in the London subnet via 10.10.1.7, successfully uploading and downloading files as show in Diagram 18.
<br /> 
<p align="center">
Diagram 18: <br/>
<img src="https://imgur.com/6BTADNR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
Paris FTP Access: MicahParisPC1 could access the Paris FTP server at 172.16.1.4 without any issue which can be seen in Diagram 19. 
<br /> 
<p align="center">
Diagram 19: <br/>
<img src="https://imgur.com/iwMekpC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
Cross-site FTP access was not allowed due to NSG rules that restrict file sharing resources to their respective cities.
<h2>Troubleshooting</h2>
During the deployment and testing phase, an issue was encountered where the VMs were unable to communicate with each other over RDP (Port 3389), even though the necessary port configurations were in place, as shown in the Network Security Group (NSG) settings. The RDP inbound rule was correctly set to allow traffic on port 3389, but communication between the servers still failed.
<br />
<p align="center">
Diagram 20: <br/>
<img src="https://imgur.com/qcdOVS8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> </p>
<br />
<br /> 
<h3>Intial Observations</h3>
<h4>1.	NSG Configuration:</h4> 
The Network Security Group rules were correctly configured to allow inbound traffic on port 3389 for RDP connections. As shown in Diagram 20, the rule allowing RDP traffic (Priority 300) was correctly applied, and there were no conflicting deny rules that would prevent the traffic.
<h4>2.	Windows Defender Firewall:</h4>
Despite the correct NSG rules, the Windows Defender Firewall on the VMs seemed to be blocking the communication. The firewall settings, which indicated that the private network firewall was turned on, and by default, it was blocking any incoming connections that were not on the list of allowed applications.
<br />
<h3>Resolution:</h3>
After some investigation, it was discovered that the Windows Defender Firewall was the root cause of the communication failure between the VMs. The issue was resolved by turning off the Windows Defender Firewall for the private network settings. Once the firewall was disabled, the servers were able to communicate with each other as expected over RDP.
<br />
<h2>Conclusion</h2>
The implementation of the network on Azure was completed successfully. All resources, including VNETs, subnets, VMs, and gateways, were set up in line with the design document. Testing confirmed that the network met all business requirements, with correct routing and security in place. The few issues encountered during testing were resolved through troubleshooting steps.
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

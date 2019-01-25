
<h1>Overview of Cisco CSR 1000v on Microsoft Azure</h1>
<p>
The Cisco Cloud Services Router (CSR) 1000v is a full-featured Cisco IOS XE router, enabling IT departments to deploy enterprise-class networking services in the Microsoft Azure cloud. Most Cisco IOS XE features are also available on the virtual Cisco CSR 1000v.

You can choose to deploy Cisco CSR 1000v software on new or existing infrastructure, such as a virtual network.

The following VPN features are supported on the Cisco CSR 1000v: IPsec, DMVPN, FlexVPN, Easy VPN and SSLVPN. You can use dynamic routing protocols such as EIGRP, OSPF, and BGP to construct multi-tier architectures within Azure, and interconnect with corporate locations or other clouds.

You can secure, inspect, and audit hybrid cloud network traffic with application-aware Zone Based Firewall. You can also use IP SLA and Application Visibility and Control (AVC) to find out about performance issues, fingerprint application flows and export detailed flow data for real-time analysis and network forensics.</p>

<h1>Transit VNET</h1>
<p>A transit VNET is a common strategy to connect multiple, geographically disperse vNETS and remote networks. It simplifies network management and minimizes the number of connections required to connect multiple VNETs and remote networks.

Microsoft Azure VNETs leverages Virtual Network (VNET) peering to establish communication between VNETs. Microsoft Azure Transit vNET, known as Gateway Transit, is a centralized vNET, connecting multiple spoke vNETs.

Cisco Transit vNET solution on Azure uses a pair of CSR devices acting as DMVPN Hubs in active-active mode. The spoke VNETs also have a Cisco CSR1000v acting as DMVPN Spoke connecting to both Cisco Cloud Services Router 1000v Series devices through EIGRP or BGP as the overlay routing. The solution is does not require manual configuration and is automated. Once deployed, the solution automatically creates dynamic spoke-to-spoke IPsec tunnels in an on-demand fashion.

See DMVPN Configuration Guide for more information.

The benefits of this solution are as follows:

Higher IPsec throughput of Transit-VNET (two Cisco CSR1000v devices in Active-Active state)
Connect multiple VNETs spanning globally, across regions, subscriptions, etc.
Dynamic Spoke-to-Spoke IPsec tunnel reduces billing charges, as the traffic can now flow directly between one spoke VNET to another without having to traverse the Transit-Hub VNET
Seamlessly connect to MultiCloud & Hybrid Cloud topologies with DMVPN as Overlay
Support for up to 1000 IPsec tunnels
Ability to handle Overlapping IP-Address space in Spoke VNETs
End-to-End encryption is possible (From spoke-VNET to another spoke-VNET or to remote branch or on-premise locations)
Enhances the cloud with Cisco IOS XE feature set that includes, QoS, ZBFW, NAT, AVC

<b>Figure 1. DMVPN all-CSR based Transit VNET Supported on Azure</b>
<img src="dmvpn_tvnet.png"/>

</p>


<h2>Transit VNET 2 NIC Hub templates</h2>

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcsr1000v%2Ftransit_vnet_all_csr%2Fmaster%2Ftvnet-16-x-2nic-hub%2FmainTemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>


<h2>Transit VNET Combined Spoke templates</h2>

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fcsr1000v%2Ftransit_vnet_all_csr%2Fmaster%2Ftvnet-16-x-combined-spoke%2FmainTemplate.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>




<h1>Documentation:</h1>

https://www.cisco.com/c/en/us/td/docs/routers/csr1000/software/azu/b_csr1000config-azure/b_csr1000config-azure_chapter_01010.html

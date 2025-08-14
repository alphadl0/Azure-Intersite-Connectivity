# Azure-Intersite-Connectivity
This lab demonstrates how to implement intersite connectivity in Azure using virtual network peering and gateway transit. It simulates a real-world scenario where core IT services must securely communicate with manufacturing systems across segmented VNets. Key tasks include VM deployment, network diagnostics, peering configuration, and UDR.

## Architecture
<img width="1828" height="759" alt="az104-lab05-architecture" src="https://github.com/user-attachments/assets/64957558-741f-4ea2-9c54-6a1ffe2ad0bd" />

## Overview of resources
<img width="1075" height="568" alt="lab 5" src="https://github.com/user-attachments/assets/27614956-e131-49d0-8946-4cfdb73ec64f" />

## Resource Group: az104-rg5 Created in East US 2 to centralize all lab components.

### Virtual Networks:
Both VNets were provisioned in East US 2 to enable seamless peering and gateway transit.
### CoreServicesVnet 
(10.0.0.0/16)

### ManufacturingVnet 
(172.16.0.0/16) 

### Virtual Machines:

**CoreServicesVM** and **ManufacturingVM** were deployed in their respective **VNets** with matching subnet configurations.

Region was explicitly set to East US 2 during VM creation via the Azure Portal.

**Network Watcher & Diagnostics**: Enabled in East US 2 to support connection troubleshooting and packet capture.

### VNet Peering
Peering: **CoreServicesVnet-to-ManufacturingVnet** and vice versa

Status: ✅ **Connected**

### Custom Route
Route Table: **rt-CoreServices**

Route: **PerimetertoCore** → 10.0.0.0/16 via NVA (10.0.1.7)

<img width="5112" height="10425" alt="az104-rg5" src="https://github.com/user-attachments/assets/745e3f1f-27ef-4efc-bbea-6fd9056bc155" />

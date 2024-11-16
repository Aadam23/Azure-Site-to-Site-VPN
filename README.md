<h1>Azure Site-to-Site VPN Setup</h1>
<p>This project demonstrates the configuration of an Azure Site-to-Site VPN connection, simulating an on-premises network using a Virtual Machine on Azure.</p>
<br />

<h2>Project Overview</h2>
<p>The project showcases:</p>

- Creating and configuring an Azure Virtual Network (VNet) and a Virtual Network Gateway.
- Simulating an on-premises network with another VNet and Virtual Machine.
- Setting up a Local Network Gateway to represent the on-premises setup.
- Establishing a secure Site-to-Site VPN connection using IPsec/IKE.

<h2>Diagram:</h2>
<p align="center"><img width="492" alt="Screenshot 2024-11-16 at 3 54 10 PM" src="https://github.com/user-attachments/assets/fc1a2707-4458-4eda-80dc-378a83d65bc4"></p>
<br>
<br>


<h2>Tools & Technologies Used</h2>

- **Azure Virtual Network (VNet)**: Configured to establish isolated networks in Azure for both simulated "on-premises" and cloud environments.
- **Azure Virtual Network Gateway**: Deployed to enable secure Site-to-Site VPN connections.
- **Azure Local Network Gateway:**: Configured to represent the on-premises network in the cloud setup.
- **Azure Virtual Machine (VM)**: Simulated the "on-premises" network environment. Hosted within a separate VNet (OnPremVNet) with a public IP.
- **Shared Key (PSK)**: Used for authentication in the VPN configuration.
- **Azure Logs**: Enabled for troubleshooting connectivity issues and verifying IPsec policies.
<br />

<h2>Steps</h2>

Setup Instructions

1. **Create an Azure Virtual Network**:
   - Set up a Virtual Network (VPNVNet) with the address space 10.0.0.0/16.
   - Add a GatewaySubnet (10.0.1.0/24) for the Virtual Network Gateway.

2. **Create the Virtual Network Gateway**:
   - Use Route-based as the VPN type.
   - Assign a Public IP and ensure the SKU is at least VpnGw1.

3. **Simulate the On-Premises Network**:
   - Create another VNet (OnPremVNet) with the address space 192.168.0.0/16.
   - Deploy a Virtual Machine in this VNet to represent an on-premises device.

4. **Configure the Local Network Gateway**:
   - Create a Local Network Gateway pointing to the public IP of the simulated VM.
   - Add the on-premises network address space (192.168.1.0/24).
  
5. **Establish the VPN Connection**:
   - Configure a Site-to-Site (IPsec) connection between the Virtual Network Gateway and the Local Network Gateway.
   - Use a shared key for secure communication.

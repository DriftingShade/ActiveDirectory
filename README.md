# Active Directory Environmental Lab Setup

This project demonstrates the setup of a virtual Active Directory environment using Oracle VM VirtualBox. This README provides a detailed process, with screenshots, for building and configuring an AD setup including a Domain Controller (DC) and client machines. This setup is valuable for IT Help Desk tasks such as user management, Group Policy configuration, and network troubleshooting.

## Project Overview

The goal of this project is to create a fully functional AD environment, simulating a real-world IT environment where users, groups, and policies can be managed. This setup includes:
- A **Domain Controller** to host the Active Directory and DNS services.
- **Client machines** joined to the domain, demonstrating communication and policy enforcement.
- **Documentation** and screenshots throughout the process for learning and future reference.

## Table of Contents

- [Project Setup](#project-setup)
- [Network Configuration](#network-configuration)
- [Domain Controller Installation and Configuration](#domain-controller-installation-and-configuration)
- [Adding Client Machines](#adding-client-machines)
- [Testing and Validation](#testing-and-validation)
- [Screenshots](#screenshots)
- [Conclusion](#conclusion)

## Project Setup

### Prerequisites

- **Oracle VM VirtualBox**: Installed and configured.
- **Windows Server** and **Windows 10 ISOs**: For setting up the Domain Controller and client machines.
- **Minimum Requirements**:
  - 4GB RAM for the DC VM, 2GB RAM for each client.
  - 40GB of disk space per VM.

### Folder Structure

This repository contains:
- `README.md`: Project documentation and setup guide.
- `assets/`: Folder for screenshots and other project-related images.

## Network Configuration

All VMs are configured to communicate within a private **Internal Network** in VirtualBox. This ensures network isolation and allows the DC to manage DNS and authentication for client machines.

### Steps
1. Set up the Internal Network in VirtualBox.
2. Assign static IP addresses to each VM:
   - Domain Controller: `192.168.0.69`
   - Client machines: `192.168.0.11`, `192.168.0.12`

## Domain Controller Installation and Configuration

The DC serves as the backbone of this setup, managing Active Directory and DNS.

### Steps
1. Install Windows Server on the VM designated as the Domain Controller.
2. Configure the server with a static IP and hostname.
3. Install the **Active Directory Domain Services** role.
4. Promote the server to a Domain Controller, creating a new forest (in this case it is `gibdoguts.local`).
5. Configure DNS to handle requests for the domain.

## Adding Client Machines

Each client machine is added to the domain to simulate a managed environment.

### Steps
1. Install Windows on each client VM.
2. Configure each client with a static IP and set the DC as the primary DNS server.
3. Join each client machine to the domain.
4. Restart each client to complete the domain join.

## Testing and Validation

With the environment configured, various tests ensure AD and network functionality.

### Tests
- **Connectivity**: Verify that clients can communicate with the Domain Controller.
- **User and Group Management**: Create and test login for domain users.
- **Group Policy Application**: Apply policies on the DC and confirm they propagate to clients.

## Screenshots

The following screenshots demonstrate key steps in the setup process:

## Domain Controller Installation and Configuration

The following screenshot shows the **Active Directory Domain Services** role successfully installed on the Domain Controller.

![Active Directory Domain Services Installed](assets/ADDSInstalled.png)
*Server Manager showing Active Directory Domain Services successfully installed and operational on the Domain Controller.*
## DNS Configuration

The following screenshot shows the **DNS Manager** with the forward lookup zone configured for `gibdoguts.local`. This setup is essential for managing domain name resolution within the Active Directory environment.

![DNS Configuration](assets/DNSConfig.png)
*DNS Manager with `gibdoguts.local` forward lookup zone configured on the Domain Controller.*

## Adding Client1 to the Domain

The following screenshots demonstrate the process of joining **Client1** to the Active Directory domain `gibdoguts.local` and logging in with a domain user account.

### Step 1: Initiate Domain Join

In the **Computer Name/Domain Changes** window, we specified the domain `gibdoguts.local` for **Client1** to join.

![Joining Client1 to the Domain](assets/Client1DomainJoin.png)
*Setting up Client1 to join the gibdoguts.local domain.*

### Step 2: Successful Domain Join

After providing the domain credentials, we received a welcome message indicating **Client1** was successfully added to the domain.

![Client1 Domain Join Success](assets/Client1Success.png)
*Client1 successfully joined to the gibdoguts.local domain.*

### Step 3: Logging in with Domain User

After restarting, we logged in to **Client1** using the domain user account `johnsmith`, confirming successful authentication to the domain.

![Logging in with Domain User](assets/Client1Login.png)
*Domain user johnsmith logging in on Client1 after joining the domain.*

## Group Policy: Disable Control Panel Access

To demonstrate Group Policy, we created a policy to prevent users from accessing the Control Panel on domain-joined machines.

### Creating and Applying the Group Policy

The **Disable Control Panel Access** GPO was created in Group Policy Management to restrict user access to the Control Panel.

![Group Policy Management](assets/GroupPolicyControlPanel.png)
*Group Policy Management Console showing the Disable Control Panel Access policy.*

### Result on Client1

After applying the Group Policy, attempts to open the Control Panel on **Client1** are blocked.

![Group Policy Result](assets/Client1ControlPanelBlocked.png)
*Client1 showing a message that access to the Control Panel is restricted by Group Policy.*


Each screenshot is saved in the `assets` folder for easy reference.

## Conclusion

This Active Directory setup project provides a hands-on demonstration of creating and managing a virtualized AD environment, equipping me with foundational skills essential for an IT Help Desk role. By completing this setup, I gained experience with user and group management, Group Policy enforcement, and network troubleshooting within a domain environment.

---

For any questions or collaboration requests, feel free to reach out!

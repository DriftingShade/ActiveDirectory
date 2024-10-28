# Active Directory Environment Setup

This project demonstrates the setup of a virtual Active Directory (AD) environment using Oracle VM VirtualBox. This README provides a detailed process, with screenshots, for building and configuring an AD setup including a Domain Controller (DC) and client machines. This setup is valuable for IT Help Desk tasks such as user management, Group Policy configuration, and network troubleshooting.

## Project Overview

The goal of this project is to create a fully functional AD environment, simulating a real-world IT environment where users, groups, and policies can be managed. This setup includes:
- A **Domain Controller (DC)** to host the Active Directory and DNS services.
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
   - Domain Controller: `192.168.1.10`
   - Client machines: `192.168.1.11`, `192.168.1.12`, etc.

## Domain Controller Installation and Configuration

The DC serves as the backbone of this setup, managing Active Directory and DNS.

### Steps
1. Install Windows Server on the VM designated as the Domain Controller.
2. Configure the server with a static IP and hostname.
3. Install the **Active Directory Domain Services (AD DS)** role.
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

1. **AD DS Installation** on the Domain Controller.
2. **DNS Configuration** on the Domain Controller.
3. **Client Domain Join** process.
4. **Group Policy Management** in action.

Each screenshot is saved in the `assets` folder for easy reference.

## Conclusion

This Active Directory setup project provides a hands-on demonstration of creating and managing a virtualized AD environment, equipping me with foundational skills essential for an IT Help Desk role. By completing this setup, I gained experience with user and group management, Group Policy enforcement, and network troubleshooting within a domain environment.

---

For any questions or collaboration requests, feel free to reach out!

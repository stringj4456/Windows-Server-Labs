# Overview
- This lab documents the configuration of a Domain Controller within a virtualized environment
- The objective of this lab is to deploy and configure a fully functional Domain Controller by installing and promoting Active Directory on Windows Server
- The configuration includes enabling the necessary services, such as DNS, to support authentication, directory services, and domain functionality
- Upon completion, the environment supports secure domain joins and centralized authentication for client machines.

# Environment
- Windows Server 2025 (Desktop Experience)
- Hypervisor: VMware Workstation
  - vCPUs: 2
  - Memory: 4 GB
  - Storage: 80 GB (virtual disk)
- Adapter type: NAT
- IP Configuration: Static
  
# Objectives
- Deploy Active Directory Domain Services (ADDS) to provide centralized authentication and directory services
- Configure the Domain Controller and integrated DNS server to enable name resolution and support domain functionality for client machines

# Implementation Summary
- Updated the server hostname from the default to reflect its role as a Domain Controller
- Configured a static IP address to provide a stable network identity for the DC
- Installed the Active Directory Domain Services role (AD DS) using Server Manager
- Promoted the server to Domain Controller by creating a new forest and domain: **testcorp.lab**

# Validation
- Verified DNS integration and ADUC console setup
- 
# Overview
- This lab documents the process of joining a Windows 11 client to an Active Directory domain
- The domain controller was previously configured with AD DS, DNS, and appropriate organizational units
- The objective of this lab is to securely join a client machine to the domain using delegated permissions and a pre-staged computer account
  
# Environment
- Client OS: Windows 11 Pro
- Domain Controller: Windows Server 2025
- Hypervisor: VMware Workstation
  - vCPUs: 2
  - Memory: 4 GB
  - Storage: 64 GB (virtual disk)
- Adapter type: NAT
- IP Configuration: Static
- DNS Server: Configured to point to the Domain Controller
  
# Objectives
- Join a Windows 11 client to the domain of the newly created Domain Controller

# Implementation Summary
- Changed DNS server settings on the client
- Prestaged a domain join for the client
- Delegated control of the **Computers** OU to a Domain Joiner account
- 

# Validation
- 
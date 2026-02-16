# Overview
- This lab documents the configuration of a Domain Controller in a virtualized setup. The goal is to prepare a fully functional DC with all of the necessary services and features to allow client machines to join the domain. 

# Environment
- Windows Server 2025 (Desktop Experience)
- Hypervisor: VMware Workstation
  - vCPUs: 2
  - Memory: 4 GB
  - Storage: 80 GB (virtual disk)
- Adapter type: NAT
- IP Configuration: Static
  
# Objectives
- Deploy Active Directory Domain Services (ADDS)
- Configure the Domain Controller and integrated DNS

# Implementation Summary
- Installed the ADDS role
- Promoted the server to Domain Controller 
- Created a new forest/domain: **testcorp.lab**

# Validation
- Verified DNS integration and ADUC console setup
- 
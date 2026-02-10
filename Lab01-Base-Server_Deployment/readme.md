# Overview
This lab documents the deployment of a base Windows Server environment in a virtualized setup. The goal is to prepare a clean, secure, and network ready server prior to installing enterprise roles such as Active Directory, DNS, and DHCP.

This lab focuses on the deployment of a fresh installation.

# Environment
- Windows Server 2025 (Evaluation)
- Desktop Experience
  
# Virtualization
- Hypervisor: VMware Workstation
- vCPUs: 2
- Memory: 4 GB
- Storage: 80 GB (virtual disk)

# Network
- Adapter type: NAT
- IP Configuration: Static

# Objectives
- Deploy a funcitonal Windows Server virtual machine
- Apply initial system configuration and security baseline
- Configure reliable network settings
- Prepare the server for future role installation

# Implementation Summary
- Installed Windows Server using Desktop Experience
- Created local Administrator account during setup
- Renamed the server to reflect enterprise naming conventions
- Configured a static IPv4 address to ensure consistent network identity
- Installed VMware Tools to enable optimized performance
- Applied Windows Updates to the bring the system up to date
- Verified Windows Defender and Firewall were enabled
- Took a snapshot after base configuration to preserver a rollback point
  
# Validation
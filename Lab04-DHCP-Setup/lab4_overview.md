# Overview
- This lab documents the installation and configuration of the DHCP role on a Windows Server machine
- The objective of the lab is to deploy and configure DHCP to dynamically assign IP addresses to client machines, enabling centralized IP management
- The lab also reinforces understanding of key DHCP concepts such as scopes, leases, reservations, and authorization within Active Directory
  
# Environment
- Client OS: Windows 11 Pro
- Domain Controller: Windows Server 2025
- Hypervisor: VMware Workstation
  - vCPUs: 2
  - Memory: 4 GB
  - Storage: 64 GB (virtual disk)
- Adapter type: NAT
- IP Configuration: Static
    
# Objectives
- Install and configure the DHCP role on the Domain Controller
- Authorize the DHCP server within Active Directory
- Create and configure a DHCP scope including IP address range, subnet mask, gateway, and DNS settings
- Verify DHCP functionality by confirming that client machines are correctly receiving IP addresses from the server

# Implementation Summary
- Using the Domain Administrator account, authorized the DHCP  server in Active Directory
- Created and configured a new DHCP scope to define the range of IP addresses that can be leased to client machines
- Configured an exclusion range within the DHCP scope to prevent the server from assigning a specific subset of IP addresses
- Added the Default Gateway to the DHCP scope to allow clients to reach outside their local subnet
- Configured the DNS server settings in the scope to ensure clients can resolve hostnames and locate Active Directory services

# Validation
- Using **ipconfig /all** on a client machine, the following was verified:
  - A valid address within the specified range was automatically assigned to the client
  - The listed DHCP server address matches that of the domain controller
  - The listed Default Gateway matches what was configured in DHCP (003)
- Confirmed successful lease renewal using **ipconfig /release** and **ipconfig /renew**
- Validated client lease presence in the DHCP servers Address Leases list

# Lessons Learned
- Authorization ensures that the DHCP server is recognized as legitimate and can lease IP addresses to clients, preventing rogue or accidental DHCP servers from disrupting the network
- Hypervisors like VMware can automatically provide DHCP on certain network types (e.g., NAT, host-only). These services must be disabled or avoided to ensure clients receive their addresses from the correct DHCP server
- Windows services that run within a shared **svchost.exe** process must use the same logon account, as the process operates under a single security context. The DHCP Server service was configured with a different account than other services in its host group, causing it to fail to start. Reconfiguring the service to use the default Local System account resolved the issue by aligning it with the required security context
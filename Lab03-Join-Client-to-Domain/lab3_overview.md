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
- Configure DNS settings to allow proper domain resolution
- Pre-stage a computer account in Active Directory
- Delegate domain join permissions using least privilege principles
- Successfully join the Windows 11 client to the domain
- Validate secure domain authentication
  
# Implementation Summary
- Configured the client’s DNS server to point to the Domain Controller
- Created separate OUs in ADUC for the users (**Lab Users**) and computers (**Lab Computers**)
- Created a dedicated Domain Joiner account within the Lab Users OU
- Pre-staged the computer account in the Lab Computers OU and assigned appropiate permissions to the delegated account
- Joined the Windows 11 client to the domain using the delegated credentials
- Restarted the client to complete domain membership

# Validation
- Validated DNS name resolution to the domain controller using:
  ```
  nslookup dc01.testcorp.lab
  ```
- Verified successful authentication by logging in with a domain user account
- Confirmed the client is authenticated against the domain via:
  ```
  whoami /fqdn
  ```
- Verified the secure channel status using:
  ```
  Test-ComputerSecureChannel
  ```

# Lessons Learned
- A default (non-prestaged) domain join occurs when the computer object does not already exist in Active Directory. A prestaged domain join occurs when the computer object is manually created in advance within Active Directory
- Default domain joins are simpler and automatically create computer objects, but provide less control over OU placement and delegation. Prestaged joins require additional setup and specific permissions, but offer tighter administrative control
- Prestaged domain joins require the joiner account to have the **Reset Password** permission on the computer object. Without it, the join fails because the machine account password cannot be reset
- The client must be configured to use the domain controller’s DNS server in order to successfully locate and join the domain
# Overview
- This lab documents the joining of a Windows 11 client to a domain. 
  
# Environment
- Windows 11 Pro
- Hypervisor: VMware Workstation
  - vCPUs: 2
  - Memory: 4 GB
  - Storage: 64 GB (virtual disk)
- Adapter type: NAT
- IP Configuration: Static
  
# Objectives
- Join a Windows 11 client to the domain of the newly created Domain Controller
- Create separate OUs for new Computers and Users

# Implementation Summary
- Created the **Lab Computers** and **Lab Users** OUs
- Created a new Computer (**Client1**) in the Lab Computers OU
- Created a new User (**LabUser1**) in the Lab Users OU

# Validation
- 
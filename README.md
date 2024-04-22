# Introduction to Windows Deployment Services (WDS)

## Overview
Windows Deployment Services (WDS) is used for deploying Windows operating systems over a network, eliminating the need for manual installations via USB or DVD.

## Pre-Installation Requirements
- **Domain Membership**: The deployment server must be a domain member or a domain controller.
- **DNS Server**: A properly configured DNS server is needed for name resolution.
- **DHCP Server**: A DHCP server with an available IP address pool is essential for PXE (Preboot Execution Environment) clients.

## Server Setup for Demonstration
- **Hostname**: WS2k19-DC01
- **Role**: Root domain controller with a single-domain Active Directory forest.
- **Installed Services**:
  - Active Directory Domain Services
  - DNS
  - DHCP

## DHCP and DNS Configuration Overview
- **DHCP IP Scope**: 172.18.72.100 to 172.18.72.254
- **DNS Service**: Operational and responding correctly.

## WDS Installation Steps
1. Accessed via Server Manager, using "Add Roles and Features".
2. Role selected: Windows Deployment Services, including both Deployment Server and Transport Server.

## WDS Configuration
- **Integration**: Integrated with Active Directory Domain Services for authentication.
- **Storage**: Option to store images on an NTFS partition; separate partition recommended.
- **DHCP Options**: Configured to support PXE client network booting.
- **Client Response**: Choice for responding to all client computers, known and unknown, without requiring manual approval.

## Final Steps and Verification
- Ensured WDS service started correctly; manual start might be necessary.
- Added a boot image and an install image to WDS from a mounted Windows 10 ISO.

## Practical Tips for Deployment
- **Network Settings**: Verify network settings and ensure all services are running before starting WDS installation.
- **Update Images**: Regularly update WDS images to include the latest security patches and drivers.
- **Network Load**: Consider the network load during deployments, especially in environments with many clients.


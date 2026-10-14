# Enterprise IT Support & Help Desk Lab

## Project Overview

A hands-on enterprise IT support lab built using Oracle VirtualBox, Windows Server 2022, and Windows 11.

This project simulates a small corporate IT environment and demonstrates practical skills in Active Directory administration, workstation support, network troubleshooting, Group Policy management, file-share permissions, and help desk incident resolution.

All activities were performed in a controlled virtual environment using simulated employee accounts.

## Lab Environment

| Component | Configuration |
|---|---|
| Virtualization | Oracle VirtualBox |
| Domain Controller | ITLAB-DC01 |
| Server OS | Windows Server 2022 |
| Client Workstation | ITLAB-PC01 |
| Client OS | Windows 11 |
| Active Directory Domain | corp.itlab.test |
| Server IP Address | 10.10.10.10 |
| Workstation IP Address | 10.10.10.20 |
| Network | Isolated VirtualBox Internal Network (ITLAB-NET) |
| Core Services | Active Directory Domain Services, DNS, Group Policy, SMB File Sharing |

## Technical Skills Demonstrated

- Windows Server installation and configuration
- Active Directory Domain Services administration
- Organizational Unit (OU) creation and management
- Domain user and security group management
- Windows 11 domain joining
- DNS configuration and connectivity testing
- Group Policy Object (GPO) configuration and verification
- NTFS and network share permissions
- Role-based access control
- Account lockout troubleshooting and recovery
- PowerShell administration and verification
- IT incident documentation

## Active Directory Administration

Created a simulated corporate Active Directory environment with organizational units representing Finance, Human Resources, IT, Operations, Security Groups, and Workstations.

Configured departmental security groups and associated user accounts to support access control.

**Evidence:** [Active Directory screenshots](screenshots/active-directory/)

## Windows 11 Domain Integration

Joined ITLAB-PC01 to the corp.itlab.test domain and verified domain membership and authentication.

**Evidence:** [Domain-joined workstation](screenshots/active-directory/04-domain-joined-workstation.png)

## File Share Permissions

Configured departmental folders on ITLAB-DC01 and tested access using different employee accounts.

Demonstrated that authorized users could access their assigned departmental resources while unauthorized access was denied.

**Evidence:** [File-share permission screenshots](screenshots/file-share-permissions/)

## Group Policy Management

Configured and applied a workstation security GPO, including a 600-second machine inactivity limit.

Verified that the policy applied to the domain-joined Windows 11 workstation.

Also configured and verified the domain account lockout threshold of five invalid attempts, with a 30-minute lockout duration and observation window.

**Evidence:** [Group Policy screenshots](screenshots/group-policy/)

## Help Desk Incident Simulations

### INC-001 — Active Directory Account Lockout

**Issue:** A simulated employee, Sarah Johnson, was unable to log in because her domain account had been locked after repeated unsuccessful authentication attempts.

**Investigation:** Verified the account lockout policy and confirmed the locked account in Active Directory Users and Computers.

**Resolution:** Unlocked the account and verified successful domain authentication.

**Status:** Resolved

**Incident report:** [INC-001 — AD Account Lockout](tickets/INC-001-AD-Account-Lockout.md)


### INC-002 — DNS Resolution Failure and Recovery

**Issue:** A simulated employee could not resolve the corporate
Active Directory domain because the workstation was configured
with an incorrect DNS server address.

**Investigation:**
- Used `nslookup` to identify DNS resolution failures.
- Verified successful IP connectivity using `ping`.
- Identified the incorrect DNS server address, 10.10.10.99.

**Resolution:**
- Restored the correct DNS server address, 10.10.10.10.
- Cleared the DNS resolver cache.
- Verified successful domain name resolution.
- Confirmed domain controller discovery using `nltest`.

**Status:** Resolved

**Incident report:** [INC-002 — DNS Resolution Failure](tickets/INC-002-DNS-Resolution-Failure.md)

**Evidence:** [DNS Troubleshooting Screenshots](screenshots/dns-troubleshooting/)


### INC-003 — Windows Print Spooler Service Failure and Recovery

**Issue:** A simulated Windows printing service failure affected workstation ITLAB-PC01.

**Investigation:**
- Verified the initial Print Spooler service status using PowerShell.
- Simulated a service failure by stopping the Print Spooler.
- Confirmed the service was stopped.
- Investigated the service startup configuration and service account.

**Resolution:**
- Restarted the Print Spooler service using PowerShell.
- Verified that the service returned to the `Running` state.

**Status:** Resolved

**Incident report:** [INC-003 — Print Spooler Service Recovery](tickets/INC-003-Print-Spooler-Service-Recovery.md)

**Evidence:** [Print Spooler Troubleshooting Screenshots](screenshots/service-troubleshooting/)


## Project Documentation

- [Active Directory evidence](screenshots/active-directory/)
- [File-share permissions evidence](screenshots/file-share-permissions/)
- [Group Policy evidence](screenshots/group-policy/)
- [Help desk incident evidence](screenshots/helpdesk-incidents/)
- [INC-001 incident report](tickets/INC-001-AD-Account-Lockout.md)
- [INC-002 DNS Troubleshooting Report](tickets/INC-002-DNS-Resolution-Failure.md)

## Project Status

**Completed — Initial Version (v1.0)**

The initial lab environment and core IT support scenarios have been successfully completed and documented.

The project currently includes:
- Windows Server 2022 and Windows 11 domain environment
- Active Directory user and group management
- Departmental file sharing and NTFS permissions
- Group Policy configuration and verification
- Three documented help desk incident simulations
- 25 supporting screenshots

Future enhancements may include additional troubleshooting scenarios, PowerShell automation, and expanded IT support documentation.

## Disclaimer

This project was created for educational and professional portfolio purposes. All employee identities, incidents, and organizational resources are simulated.
# Honeynet and SOC Environment using Azure

![Log ana](https://github.com/emeka789/SiemLab/assets/99328320/5e785f6b-fa0e-4a5e-be95-69e9777b7299)

## Summary

In this project, we created an unsecured honeynet and SOC environment within Azure & exposed it to the internet for a 24hr period to capture, consolidate, analyze, and monitor logs from several sources (Syslog, SecurityEvent etc.) with the purpose of creating dashboards to visualize log data, trigger alerts and create incidents. After this, security controls were implemented to harden the environment and was once again exposed to the internet for an additional 24hr period. Metrics were compared between the two periods to evaluate the environment's security posture and incident response effectiveness.

## Metrics captured and analyzed

- Linux Event Logs (Syslog)
- Windows Event Logs (SecurityEvent)
- NSG allowed malicious flows (AzureNetworkAnalytics_CL)
- SecurityIncident (Incident Created by Sentinel)

## Technologies, Regulations and Azure Components Used
- Azure Network Security Groups (NSGs)
- Azure Virtual Network (Vnet)
- Azure Virtual Machines (Windows/Linux)
- Log Analytics Workspace (KQL queries)
- Azure Key Vault (Auditing and Monitoring of Secrets/Keys/Certificates) 
- Azure Blob Storage Account (Object Storage and Access Management)
- Commnand Line Interface for Virtual Machines (PowerShell, Command Shell, Terminal)
- Windows Remote Desktop Protocol for Remote Access (RDP)
- Microsoft Sentinel for Security Information and Event Management (SIEM)
- Microsoft Defender for Cloud for Threat Protection
- [NIST SP 800-53 Revision 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)  (Security and Privacy Controls)
- [NIST SP 800-61 Revision 2](https://www.nist.gov/privacy-framework/nist-sp-800-61) (Incident Handling Guide)

# Before Hardening

This phase's aim was to study real-world attack patterns by deliberately exposing a virtual environment to the public internet with minimal security controls. The environment comprised a Windows 10 Virtual Machine with a SQL database, a Linux Virtual Machine, a blob storage account, and a key vault, strategically chosen to expand the attack surface. Security controls were intentionally limited, with disabled firewalls on virtual machines, Network Security Groups configured to allow all inbound traffic, as well as public endpoints visible to the web for the storage account and key vault. Log Analytics and Microsoft Sentinel were implemented for comprehensive logging, monitoring, and incident creation/response. To visualize the recorded malicious activities, four custom query-based workbooks were created in Microsoft Sentinel, presenting a world map for geographical analysis of attacks. The subsequent section provides insights into the results of these real-world attacks, displaying practical and realistic cybersecurity simulations.

## Attack Maps: Unsecure State

#### This attack map depicts malicious attempts to SSH into the Linux VM
![Linux SSH](https://github.com/emeka789/emeka789/assets/99328320/15323529-2c39-457c-9bc5-39d00deb1c1d)

#### This attack map depicts malicious attempts to RDP into the Windows VM
![Windows RDP](https://github.com/emeka789/emeka789/assets/99328320/5c4683eb-2e66-4ccb-ad25-4fc4922491b0)

#### This attack map shows malicious flows allowed into the virtual machine via NSG
![NSG](https://github.com/emeka789/emeka789/assets/99328320/ce49c11a-78a6-41be-9fad-be8bb0524ebc)

# After Hardening

## Attack Maps: Secured State
  Map queries returned back empty after implementation of security controls
  




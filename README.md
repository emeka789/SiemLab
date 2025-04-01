# Honeynet and SOC Environment using Azure

![Log ana](https://github.com/emeka789/SiemLab/assets/99328320/5e785f6b-fa0e-4a5e-be95-69e9777b7299)

## Summary

In this project, an unsecured honeynet and SOC environment was created within Microsoft Azure & exposed to the internet for a 24hr period to capture, monitor, and analyze logs from several sources with the purpose of visualizing log data via dashboards, triggering alerts and creating incidents. After this, security controls were implemented to harden the environment and it was once again exposed to the internet for an additional 24hr period. Metrics were compared between the two periods to evaluate the environment's security posture and incident response effectiveness.

## Technologies, Regulations and Azure Resources Used
- Azure Network Security Groups (NSGs)
- Azure Virtual Network (Vnet)
- Azure Virtual Machines (Windows/Linux)
- Log Analytics Workspace (KQL queries)
- Azure Key Vault (Auditing and Monitoring of Secrets/Keys/Certificates) 
- Azure Blob Storage Account (Object Storage and Access Management)
- Command Line Interface for Virtual Machines (Terminal, Command Prompt)
- Windows Remote Desktop Protocol for Remote Access (RDP)
- Microsoft Sentinel for Security Information and Event Management (SIEM)
- Microsoft Defender for Cloud for Threat Protection
- [NIST SP 800-53 Revision 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)  (Security and Privacy Controls)
- [NIST SP 800-61 Revision 2](https://www.nist.gov/privacy-framework/nist-sp-800-61) (Incident Handling Guide)


## Metrics captured and analyzed

- Linux Event Logs (Syslog)
- Windows Event Logs (SecurityEvent)
- NSG allowed malicious flows (AzureNetworkAnalytics_CL)
- SecurityIncident (Incident Created by Sentinel)


# Before Hardening

This phase's aim was to study real-world attack patterns by deliberately exposing a virtual environment to the public internet with minimal security controls. The environment comprised a Windows 10 Virtual Machine with a SQL database, a Linux Virtual Machine, a blob storage account, and a key vault, strategically chosen to expand the attack surface. Security controls were intentionally limited, with disabled firewalls on virtual machines, Network Security Groups configured to allow all inbound traffic, as well as public endpoints visible to the web for the storage account and key vault. Log Analytics and Microsoft Sentinel were implemented for comprehensive logging, monitoring, and incident creation/response. To visualize the recorded malicious activities, four custom query-based workbooks were created in Microsoft Sentinel, presenting a world map for geographical analysis of attacks. The subsequent section provides insights into the results of these real-world attacks, displaying practical and realistic cybersecurity simulations.

| Metrics  | Count |
| ------------- | ------------- |
| Linux Event Logs (Syslog)  |  230 |
| Windows Event Logs (SecurityEvent)  | 9995  |
| SecurityIncident (Incidents created by Sentinel) |  122 |
| SecurityAlert (Alerts create by Log Analytics Workspace)  | 2  |
| AzureNetworkAnalytics_CL (Malicious Flows allowed into the NSG)  | 888  |


## Attack Maps: Unsecure State

#### This attack map depicts malicious attempts to SSH into the Linux VM
![Linux SSH](https://github.com/emeka789/emeka789/assets/99328320/15323529-2c39-457c-9bc5-39d00deb1c1d)

#### This attack map depicts malicious attempts to RDP into the Windows VM
![Windows RDP](https://github.com/emeka789/emeka789/assets/99328320/5c4683eb-2e66-4ccb-ad25-4fc4922491b0)

#### This attack map shows malicious flows allowed into the virtual machine via NSG
![NSG](https://github.com/emeka789/emeka789/assets/99328320/ce49c11a-78a6-41be-9fad-be8bb0524ebc)

# After Hardening
In this project phase, the primary objective was to enhance the security infrastructure by hardening and establish robust controls in alignment with NIST SP 800-53 Revision 5 etc.
To further secure the environment, other hardening techniques were used including:
- #### Network Security Groups
  - NSGs were secured by blocking all inbound and outbound traffic with the exception of designated IP addresses that needed connection to the virtual machines. This was to make sure only authorized devices had access to the VMs.

## Attack Maps: Secured State
  Map queries returned back empty after implementation of security controls
  
| Metrics  | Count |
| ------------- | ------------- |
| Windows Event Logs (SecurityEvent)  |  2786 |
| Linux Event Logs (Syslog)  | 2  |
| SecurityIncident (Incidents created by Sentinel) |  0 |
| SecurityAlert (Alerts create by Log Analytics Workspace)  | 0  |
| AzureNetworkAnalytics_CL (Malicious Flows allowed into the NSG)  | 0  |  

## Conclusion
In conclusion, this project aimed to assess the effectiveness of security controls in enhancing the security posture of a honeynet and SOC environment within Microsoft Azure. By exposing the environment to the internet for a 24-hour period before/after implementing security controls, we were able to capture, consolidate, analyze, and monitor logs from various sources. Through the creation of dashboards, we were able to visualize log data, trigger alerts & incidents, and gain valuable insight into the environment's security landscape. 

Additionally, various metrics were recorded to compare the effectiveness of security measures. The implementation of these measures led to a 72% decrease in Windows Security Events, a 99% decrease in Linux Events, and a complete elimination of security alerts, incidents, and malicious inbound network traffic. However, it's important to note that the 100% reduction in these categories is mainly because regular user activity wasn't simulated. In a real network, authorized users would likely generate security events and alerts, even if some of them turn out to be false positives.




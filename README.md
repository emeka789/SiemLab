# Honeynet and SOC Environment using Azure

![Log ana](https://github.com/emeka789/SiemLab/assets/99328320/5e785f6b-fa0e-4a5e-be95-69e9777b7299)

## Summary

In this project, we create an unsecured honeynet and SOC environment within Azure & exposed it to the internet for a 24hr period to capture, consolidate, analyze, and monitor logs from several sources (Syslog, SecurityEvent etc) with the purpose of creating dashboards to visualize log data, trigger alerts and create incidents. After this, security controls were implemented to harden the environment and was once again exposed to the internet for an additional 24hr period. Metrics were compared between the two periods to evaluate the environment's security posture and incident response effectiveness.

## Metrics captured and analyzed

- Linux Event Logs (Syslog)
- Windows Event Logs (SecurityEvent)
- NSG allowed malicious flows (AzureNetworkAnalytics_CL)
- Alerts triggered via Azure Sentinel (SecurityIncident)
- Alerts triggered via Log Analytics Workspace (SecurityAlert)

## Attack Maps: Unsecured State

### Attempts to SSH into Linux VM
![Linux SSH](https://github.com/emeka789/emeka789/assets/99328320/15323529-2c39-457c-9bc5-39d00deb1c1d)

### Attempts to RDP into Windows VM
![Windows RDP](https://github.com/emeka789/emeka789/assets/99328320/5c4683eb-2e66-4ccb-ad25-4fc4922491b0)

### Malicious flows allowed in via NSG
![NSG](https://github.com/emeka789/emeka789/assets/99328320/ce49c11a-78a6-41be-9fad-be8bb0524ebc)

## Attack Maps: Secured State (POST-HARDENING)
  Map queries returned back empty after 
  




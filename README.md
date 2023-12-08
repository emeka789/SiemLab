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





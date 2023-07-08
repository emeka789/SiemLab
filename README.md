# Azure Sentinel: Log Creation, Analysis, & Visualization Using a SIEM

This post documents the process of creating a SIEM home lab to visualize failed login attempt data using various Microsoft Azure tools as well as a Geolocation API in conjuction with Powershell for log creation.

## Process

The SIEM home lab setup involves the following steps:

1. **Creating Log Files with PowerShell/Geolocation API:** This PowerShell script was used along w/ a Geolocation API to track/collect login attempt data from various sources, collecting data points such as Latitude/Longitude, IP Address, Country, User, and Time.

![Screenshot 2023-07-07 002824](https://github.com/emeka789/SiemLab/assets/99328320/df3ad977-215b-472e-8ac8-e4c9fb423f6c)


2. **Parsing Log Data with Azure Log Analytics Workspace:** Create an Azure Log Analytics Workspace to manage and analyze log data. Use the Log Analytics Workspace to parse log files and extract specific geolocation data, such as latitude and longitude.

![Screenshot 2023-07-07 003030](https://github.com/emeka789/SiemLab/assets/99328320/8cf367d5-9cdf-4838-b030-7018b8a235ae)

3. **Visualizing Geolocation Data with Azure Sentinel:** Connect your Azure Log Analytics Workspace to Azure Sentinel. Use Azure Sentinel's built-in tools to create a custom map-based visualization. Map the latitude and longitude fields from your log entries.

![Screenshot 2023-07-07 002038](https://github.com/emeka789/SiemLab/assets/99328320/a165684d-2852-4dc0-ade8-b86d18d810e2)


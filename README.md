# Azure Sentinel: Log Creation, Analysis, & Visualization Using a SIEM

This post documents the process of creating a SIEM home lab to visualize failed login attempt data using various Microsoft Azure tools as well as a Geolocation API in conjuction with Powershell for log creation.

## Process

The SIEM home lab setup involves the following steps:

1. **Creating Log Files with PowerShell/Geolocation API:** This PowerShell script was used along w/ a Geolocation API to track/collect login attempt data from various sources, collecting data points such as Latitude/Longitude, IP Address, Country, User, and Time.

2. **Parsing Log Data with Azure Log Analytics Workspace:** Create an Azure Log Analytics Workspace to manage and analyze log data. Use the Log Analytics Workspace to parse log files and extract specific geolocation data, such as latitude and longitude.

3. **Visualizing Geolocation Data with Azure Sentinel:** Connect your Azure Log Analytics Workspace to Azure Sentinel, a cloud-native SIEM tool. Use Azure Sentinel's built-in tools to create custom visualizations, including map-based visualizations. Map the latitude and longitude fields from your log entries to create geolocation visualizations.


## Conclusion

By following the steps outlined in this documentation, you can collect, parse, and visualize log data effectively, enabling you to gain valuable insights into potential security threats and improve situational awareness.


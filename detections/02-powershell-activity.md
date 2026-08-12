# POWERSHELL ACTIVITY 

## Objective
The goal is to monitor Powershell activity and to eventually trace back who did the script and what the script does. 

## Configuration
```xml
<location>Microsoft-Windows-PowerShell/Operational</location>
```
Paste this to enable monitoring in Microsoft Windows Powershell because the agent does not automatically monitor such events so you have you configure it yourself in the configuration file of the Agent

## Detection
To verify its detection, we can go to Event Viewer > Applications and Services Logs > Microsoft > Powershell > Operational

## Result
Results showed activity in the Wazuh Threat Hunting Module, there were Powershell activity with the following script that queried system environment variables. This could be anything like looking up processes, services, etc. This was done in a controlled manner using these commands:
```powershell
Get-Process
Get-Service
Get-ChildItem $env:USERPROFILE\Downloads
Get-NetTCPConnection
```

![alt text](<Screenshot 2026-08-11 154227.png>)

## Lessons Learned
I learned that of course inside a certain group will have the privilege to access the Command Prompt or the Powershell, monitoring activities that are done inside the CLI environment should also be monitored because people who know what they are doing especially when it comes to accessing and running shell commands hold so much power, so monitoring shell commands is also a key aspect of a SOC Analyst.
# WAZUH HOME SOC LAB

A small-scale security operations center (SOC) home lab built using Wazuh, Ubuntu Server, and Windows 11

The purpose of this project is to develop practical skills in 
- SIEM administration
- Endpoint monitoring
- File integrity monitoring
- Windows security event analysis
- Detection engineering
- Security Investigation
- MITRE ATT&CK
- Incident Response

## Architecture
Windows 11 Endpoint
        |
        | Wazuh Agent
        |
        v
Ubuntu Server
        |
        +-- Wazuh Manager
        +-- Wazuh Indexer
        +-- Wazuh Dashboard

## Technologies
- Wazuh
- Ubuntu Server
- Windows 11
- Oracle VirtualBox
- PowerShell
- Windows Event Logs
- MITRE ATT&CK

## Lab Objective
The objective of this lab is for me to get used to the SIEM environment and see what it likes to be in the shoes of a SOC Analyst. Using Wazuh, a free SIEM, the goal is to learn the fundamentals of being a SOC Analyst. At the end of this lab, I should be able to be familiar with the dashboard, gain skills that are a must-have for a SOC Analyst, and hopefully think like a SOC Analyst. The objective of this lab is to familiarize myself with the SIEM environment and experience what it is like to work from the perspective of a SOC Analyst. Using Wazuh as a free and accessible SIEM platform, I aim to build a practical understanding of security monitoring, log analysis, event investigation, and threat detection.

Rather than simply learning these concepts theoretically, I want to put myself in the shoes of a SOC Analyst by generating security events, investigating what the SIEM detects, understanding why certain events are flagged, and learning how to distinguish normal activity from potentially suspicious behavior.

By the end of this lab, I aim to be comfortable navigating the Wazuh Dashboard, understand the fundamentals of SIEM-based monitoring, develop practical skills that are essential for a SOC Analyst, and most importantly, develop the mindset and thought process needed to approach security events like a SOC Analyst.
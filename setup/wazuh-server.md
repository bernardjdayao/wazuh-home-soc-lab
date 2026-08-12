# WAZUH SERVER SETUP

## Environment
- Host OS: Windows 11
- Hypervisor: Oracle VirtualBox
- Server OS: Ubuntu 22.04 LTS
- Wazuh Version: 4.14
- Network: Bridged Network

## Server Specifications
- CPU: 3 Cores
- RAM: 4 GB
- Storage: 50 GB (with VDI)

## Installation
1. Created Ubuntu Server VM
2. Configured Bridged Networking
3. Quick Installed Wazuh Resources via Wazuh Documentation
4. Verified that Wazuh Resources and Services are working 
5. Installed Wazuh Agent in Windows 11 to serve as the endpoint
6. Verified connection through a series of test pings and ultimately open using the server's IP in the browser

## Verification
Commands used:

```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
```

## Troubleshooting
The dashboard originally failed halfway so there were difficulty trying to start the Wazuh Server in the Ubuntu VM. Originally, the service is showing but tryinng to start the command, it displayed an error saying that the service did not exist. Due to the failure midway, a configured certificate was missing. The diagnosis was reached using these commands:
sudo systemctl status wazuh-dashboard
sudo journalctl -u wazuh-dashboard

Another way to go about this is to overwrite the overall installation and make sure to allot enough resources (ie. RAM CPU and Storage) in your VM and make sure that you have enough computing power as to avoid struggles in installing Wazuh in a sandbox setting. 

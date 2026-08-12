# WINDOWS WAZUH AGENT

## Endpoint
- OS: Windows 11
- Role: Monitored Endpoint
- Agent: Wazuh Agent
- Network: Bridged

## Enrollment
The windows endpoint was enrolled with the Wazuh Manager. You can choose to copy paste the command in your respective OS' terminal or just use the GUI, it is up to your preference. Use the server's IP when enrolling your agent.

When your agent is enrolled, wait a couple seconds then it will show up in the Wazuh Dashboard.

## Verification
The agent was verified from the Wazuh server using the command:
sudo /var/ossec/bin/agent_control -l
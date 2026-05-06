# Homelab-SIEM: Wazuh Detection & Vulnerability Management

This project demonstrates a SIEM environment built with Wazuh in a virtualized infrastructure. The goal of this lab was to gain hands-on experience in threat detection, vulnerability management, and log analysis.

# Architecture

The environment is fully automated via Vagrant and consists of:
Wazuh Manager: Centralized server for indexing, alerting, and analyzing security data.
AlmaLinux 9: A Linux server monitored by a Wazuh agent.
Kali Linux: Used to simulate real-world attacks (e.g., portscans and Brute Force via Hydra).

The lab environment can be provisioned with a single command, ensuring consistency and rapid deployment.

# Configuration & Troubleshooting

Network Persistence: Configured a private network stack to allow secure communication 
between the Manager and Agents on ports 1514/1515.

Feed Integration: Resolved initial synchronization issues by mapping NVD and AlmaLinux 
providers correctly within the ossec.conf, enabling accurate scanning for RHEL-based distributions.
    
Agent Deployment: Automated the agent registration process to ensure the "Target" 
server was immediately visible in the Wazuh Dashboard upon boot.

# Key Takeaways
Hands-on experience with Log Analysis and distinguishing between "noise" and actual security incidents.

Understanding of the Vulnerability Lifecycle, from discovery via CVE databases to remediation.

Practice in Linux administration and troubleshooting agent-to-manager communication.
Cybersecurity Capstone: Detecting Unauthorized Netcat Processes with Wazuh

Project Overview
This project enhances security monitoring at 10ALYTICS-DC by leveraging Wazuh to detect and respond to unauthorized Netcat processes, a common tool for data exfiltration and backdoors. The solution involves deploying Wazuh for real-time process monitoring, generating alerts for suspicious activities, and implementing active responses to terminate malicious processes. Alerts are integrated with Slack for real-time notifications.

Presented by: Jude Chidubem Anyaegbu 
Date: June 18, 2025
Organization: 10ALYTICS-DC

Problem Statement
Threat intelligence reports indicate increased attempts to exploit systems using unauthorized tools like Netcat. This project aims to address this security gap by implementing robust monitoring and response mechanisms.


Goals

Detect unauthorized Netcat processes, especially those in listening mode.
Generate real-time security alerts for suspicious activity.
Implement active response to terminate malicious processes.
Document findings and provide mitigation strategies.

Tools and Materials

Laptop: For hosting virtual machines.

Ubuntu VM: Hosts the Wazuh agent and Netcat for testing.

Kali Linux VM: Simulates attacker behavior by connecting to the Ubuntu VM.

Wazuh VM: Runs Wazuh manager, dashboard, and indexer.

Slack App: Configured for real-time alert notifications.

Netcat: Used to simulate malicious activity.

Repository Structure
├── README.md               # Project documentation
├── docs/                   # Project documentation and presentation
│   ├── SOC_PROJECT.pptx    # Capstone presentation
│   └── images/             # Screenshots and diagrams
│       ├── image1.jpg
│       ├── image2.jpg
│       └── ... (other images)
├── configs/                # Configuration files
│   ├── ossec.conf          # Wazuh configuration file
│   └── local_rules.xml     # Custom Wazuh rules for Netcat detection
├── scripts/                # Setup and test scripts
│   ├── setup_wazuh.sh      # Script to set up Wazuh manager and agent
│   ├── install_netcat.sh   # Script to install Netcat on Ubuntu
│   └── connect_kali.sh     # Script to simulate Netcat connection from Kali
└── results/                # Output and logs
    ├── slack_alerts.txt    # Sample Slack alert messages
    └── wazuh_dashboard.png # Screenshot of Wazuh threat hunting dashboard

Setup Instructions
Prerequisites

Virtual machines: Ubuntu, Kali Linux, and Wazuh.
Slack workspace with an app configured for incoming webhooks.
Administrative access to all VMs.

Step-by-Step Setup

Wazuh Deployment:

Start the Wazuh manager, dashboard, and indexer:sudo systemctl start wazuh-manager wazuh-dashboard wazuh-indexer


Verify Wazuh manager status:sudo systemctl status wazuh-manager


Check the IP address of the Wazuh VM:ifconfig




Slack Integration:

Log in to Slack API.
Create a new app from scratch and select a channel (e.g., cyber_eagle).
Enable incoming webhooks and copy the webhook URL.
Configure Wazuh to send alerts to Slack by editing the configuration file:sudo nano /var/ossec/etc/ossec.conf


Add the webhook URL to the <ossec_config> section (refer to configs/ossec.conf).


Wazuh Agent Setup on Ubuntu:

Deploy the Wazuh agent on the Ubuntu VM.
Restart the agent:sudo systemctl restart wazuh-agent


Install Netcat and related tools:sudo apt install ncat nmap netcat-traditional -y


Enable the Ubuntu firewall:sudo ufw enable
sudo systemctl status ufw


Start a Netcat listener to simulate activity:sudo nc -lvnp 4444




Custom Wazuh Rules:

Create a custom rule for Netcat detection:sudo nano /var/ossec/etc/rules/local_rules.xml


Add rules to detect Netcat processes (refer to configs/local_rules.xml).


Kali Linux Setup:

Open a terminal in Kali Linux.
Connect to the Ubuntu VM’s Netcat listener:nc <ubuntu_ip_address> 4444




Active Response:

Configure Wazuh to terminate unauthorized Netcat processes (refer to configs/ossec.conf for active response settings).



Expected Results

Slack Alerts: Real-time notifications sent to the configured Slack channel (cyber_eagle) when unauthorized Netcat processes are detected.
Wazuh Dashboard: Visual representation of threat hunting events, including detected Netcat activities (see results/wazuh_dashboard.png).
Logs: Sample alert messages archived in results/slack_alerts.txt.

Mitigation Strategies

Restrict Netcat: Remove Netcat from non-essential systems:sudo apt-get remove netcat netcat-traditional ncat


AppArmor/SELinux: Configure to restrict Netcat execution to authorized users.
Network Monitoring: Add netstat monitoring to ossec.conf for enhanced visibility.
User Training: Promote secure alternatives like tcpdump.
Incident Response: Develop a playbook for handling Netcat-related alerts.

Conclusion
This project enhances 10ALYTICS-DC’s security by implementing robust detection and response mechanisms for unauthorized Netcat usage. It reduces the risk of data breaches and provides a blueprint for monitoring other malicious tools. Future steps include expanding monitoring to additional tools and integrating with a SIEM system.

Next Steps

Expand Wazuh rules to detect other unauthorized tools (e.g., nmap, telnet).
Integrate with a SIEM solution for centralized threat management.
Automate mitigation actions using scripts for faster response times.

Screenshots
Screenshots and diagrams are available in the docs/images/ folder, including:

Wazuh dashboard visualizations.
Slack alert notifications.
Setup and configuration steps.

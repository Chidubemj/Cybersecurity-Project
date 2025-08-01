Cyber Threat Intelligence Report: Lazarus Group Targeting Zenith Bank
Overview
This project is a Cyber Threat Intelligence (CTI) report analyzing the potential threat posed by the Lazarus Group, a North Korean state-sponsored cyber threat actor, to Zenith Bank, a leading financial institution in Nigeria. The report details the group's tactics, techniques, and procedures (TTPs), provides an attack simulation, and offers actionable recommendations to mitigate risks.
The report was originally created as a PowerPoint presentation (Threath Hunting presentation.pptx) and includes references to several images (image1.png to image6.png) used for visualization, such as the MITRE ATT&CK table screenshot.

Project Objectives

Identify Threats: Highlight the Lazarus Group's capabilities and their potential impact on Zenith Bank's online banking infrastructure (e.g., www.zenithbank.com) and customer data.
Analyze TTPs: Document observed techniques, including reconnaissance (e.g., TheHarvester, WHOIS, Google Dorking), phishing, and malware deployment.
Simulate Attack: Outline a multi-stage attack scenario, including initial access, privilege escalation, lateral movement, data exfiltration, and impact.
Provide Recommendations: Suggest proactive cybersecurity measures, such as multi-factor authentication (MFA), endpoint detection, and employee training, to enhance Zenith Bank's defenses.

Folder Structure
The project is organized as follows:
cyber-threat-intelligence-zenith-bank/
├── docs/
│   └── Threath Hunting presentation.pptx  # Main presentation file
├── images/
│   ├── image1.png                        # Referenced images
│   ├── image2.png
│   ├── image3.png
│   ├── image4.png
│   ├── image5.png
│   └── image6.png
├── README.md                             # Project documentation (this file)
└── LICENSE                               # License file (AMDARI LONDON )

Description of Folders and Files

docs/: Contains the main presentation file (Threath Hunting presentation.pptx), which includes the full report content, including the executive summary, threat actor profile, attack simulation, potential impacts, and recommendations.
images/: Stores image files (image1.png to image6.png) referenced in the presentation, such as the MITRE ATT&CK table screenshot and other visuals.
README.md: This file, providing an overview of the project, setup instructions, and usage details.
LICENSE: A license file specifying the terms under which the project can be used or shared (e.g., MIT License).

Setup Instructions

Clone the Repository:git clone https://github.com/your-username/cyber-threat-intelligence-zenith-bank.git


Access the Presentation:
Navigate to the docs/ folder.
Open Threath Hunting presentation.pptx using Microsoft PowerPoint or a compatible presentation software (e.g., LibreOffice Impress).


View Images:
Images referenced in the presentation are located in the images/ folder.
Ensure the images are correctly linked in the presentation for proper rendering.



Usage

For Security Analysts: Use the report to understand the Lazarus Group's TTPs and tailor cybersecurity defenses for financial institutions like Zenith Bank.
For Training Purposes: Leverage the presentation for cybersecurity awareness training, focusing on phishing, reconnaissance, and incident response strategies.
For Research: Study the attack simulation and MITRE ATT&CK mappings to develop threat hunting playbooks or enhance threat intelligence programs.

Key Findings

Threat Actor: Lazarus Group (aka Hidden Cobra, ZINC), a North Korean state-sponsored group active since 2009, known for attacks like the Bangladesh Bank heist (2016) and WannaCry (2017).
Targeting: Zenith Bank's online infrastructure and customer data are at high risk due to the group's focus on financial institutions.
Techniques: Reconnaissance (TheHarvester, WHOIS, Google Dorking), spear phishing, malware deployment  WannaCry, AppleJeus, and exploitation of vulnerabilities (e.g., Apache Log4j CVE-2021-44228).
Recommendations: Implement MFA, endpoint detection and response (EDR), network segmentation, and employee training to mitigate risks.

License
This project is licensed under the AMDARI LONDON License. See the LICENSE file for details.
Contact
For questions or contributions, please contact:

Author: Chidubem Jude Anyaegbu
Email: jude.anyaegbu@gmail.com
GitHub: https://github.com/Chidubemj

Acknowledgments

MITRE ATT&CK framework for TTP mappings.
Public threat intelligence sources for Lazarus Group profiling.

# Nmap Network Security Assessment

## Overview
This project demonstrates network reconnaissance techniques using **Nmap and Zenmap** within a controlled virtual lab environment. The objective was to identify active hosts, discover open ports, detect running services, and analyze potential security risks within an internal subnet.

The assessment was conducted on a virtual network consisting of multiple systems including a **Windows Server, Windows workstation, and Kali Linux attacker machine**.

## Objectives
* Identify active hosts on the network
* Perform port scanning and service discovery
* Detect operating systems and running services
* Analyze exposed services and potential security risks
* Document findings in a structured security report

## Tools and Technologies
* Kali Linux
* Nmap
* Zenmap
* Windows Server
* Windows Workstation
* VirtualBox Virtual Network
  
## Techniques Used

### Host Discovery
Identifies active systems within the subnet.
```bash
   sudo nmap -sn <subnet>
```

### Basic Port Scanning
Determines open ports on a target system.
``` bash
   sudo nmap <target>
```

### Full Port Scan
Scans all 65,535 TCP ports.
```bash
   sudo nmap -p- <target>
````

### Service and Version Detection

Identifies services running on open ports.
```bash
   sudo nmap -sV <target>
```

### Operating System Detection
Attempts to determine the operating system of a target machine.
```bash
   sudo nmap -O <target>
```

## Key Findings
* Multiple active hosts were identified within the internal subnet.
* The Windows Server exposed **Remote Desktop (3389)** and **Windows Remote Management (5985)**.
* The Windows workstation exposed **port 5357**, associated with device discovery services.
* Most ports on both systems were filtered, indicating **active firewall protections**.

## Security Analysis
Administrative services such as **RDP and WinRM** can increase the attack surface if not properly secured. These services are common targets for credential-based attacks and unauthorized remote access.

The presence of many filtered ports suggests that host-based firewall controls are actively restricting network access.

## Security Recommendations
1. Restrict administrative service access using firewall rules.
2. Enforce strong authentication policies including multi-factor authentication.
3. Secure remote communication channels and monitor administrative access activity.

## Project Structure
```
nmap-network-security-assessment
│
├── report.pdf
├── screenshots
│   ├── host-discovery.png
│   ├── port-scan.png
│   ├── service-detection.png
│   └── zenmap-scan.png
└── README.md
```

## Ethical Notice
This project was conducted in a **controlled educational lab environment**.
All network identifiers and screenshots have been **sanitized to remove sensitive information** before publication.

## Skills Demonstrated
* Network reconnaissance
* Host discovery
* Port scanning
* Service enumeration
* Security risk analysis
* Firewall filtering interpretation
* Security reporting


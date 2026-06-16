Task 1: Basic Network Scanning with Nmap

Objective

The objective of this task was to perform a network scan using Nmap to identify open ports and running services on a target system. The task helps in understanding how network reconnaissance is performed and how exposed services can be identified during a security assessment.

---

About Nmap

Nmap (Network Mapper) is an open-source network scanning and security auditing tool used by cybersecurity professionals to discover hosts, identify open ports, detect running services, and gather information about systems connected to a network.

Network scanning is often the first step in security analysis because it provides visibility into the services that are exposed and potentially accessible to attackers.

---

Environment Used

Component| Details
Operating System| Windows 11 Pro
Tool Used| Nmap 7.99
Target| localhost (127.0.0.1)
Scan Type| Service Version Detection

---

Methodology

Step 1: Verify Nmap Installation

The installation was verified using:

nmap --version

This confirmed that Nmap was successfully installed and ready for use.

Step 2: Perform Network Scan

A service version detection scan was performed using:

nmap -sV localhost

The purpose of using the "-sV" option was to identify both open ports and the services running on those ports.

Step 3: Save Scan Results

The scan output was saved into a text file for documentation and future reference.

nmap -sV localhost > nmap_scan_results.txt

---

Scan Results

The scan successfully identified seven open TCP ports on the local machine.

Port|State| Service
80  | Open| HTTP
135 | Open| MSRPC
445 | Open| Microsoft-DS
1433| Open| MS-SQL-S
1434| Open| MS-SQL-S
2383| Open| MS-OLAP4
7070| Open| SSL/RealServer

The host was active and responded successfully during the scan.

---

Analysis of Discovered Services

Port 80 - HTTP

Port 80 is commonly used for web-based communication. Nmap detected Microsoft's HTTP API service running on this port. Any web service exposed on a system should be regularly monitored and updated to prevent potential security issues.

Port 135 - Microsoft RPC

This port is used by the Remote Procedure Call service in Windows environments. It allows communication between applications and system components. While necessary for many Windows functions, unrestricted access can increase the attack surface of the system.

Port 445 - SMB (Server Message Block)

Port 445 is responsible for file and printer sharing services within Windows networks. SMB has historically been targeted by attackers and ransomware campaigns, making it one of the most sensitive ports from a security perspective.

Port 1433 - Microsoft SQL Server

This port is used by Microsoft SQL Server to handle database connections. Since databases often contain critical information, securing access to this service is important.

Port 1434 - SQL Server Browser

The SQL Server Browser service helps clients locate SQL Server instances. While useful for database connectivity, it can reveal information about database services running on a system.

Port 2383 - SQL Server Analysis Services

This service is associated with data analysis and business intelligence functions provided by Microsoft SQL Server.

Port 7070 - SSL Enabled Service

An SSL/TLS protected service was detected on port 7070. Additional investigation would be required to determine the exact application using this port and whether it is necessary for system operations.

---

Security Observations

During the scan, several Microsoft services were identified. The presence of SQL Server services indicates that database-related applications are installed on the system.

The most security-sensitive service identified during the scan is SMB on port 445, as it has historically been associated with various network-based attacks when improperly configured.

The SQL Server ports should also be protected through strong authentication and limited network exposure.

---

Recommendations

Based on the scan results, the following recommendations are suggested:

- Regularly review open ports and running services.
- Disable unnecessary services whenever possible.
- Restrict SMB access using firewall rules.
- Ensure Microsoft SQL Server services are protected using strong credentials.
- Keep the operating system and applications updated with security patches.
- Conduct periodic network scans to identify unexpected service exposure.

---

Learning Outcomes

Through this task, I gained practical experience in:

- Installing and configuring Nmap
- Performing basic network reconnaissance
- Identifying open ports and active services
- Understanding the purpose of common Windows network services
- Interpreting network scan results
- Performing a basic security assessment

---

Conclusion

This task provided hands-on experience with one of the most widely used cybersecurity tools, Nmap. By performing a service detection scan on the local machine, I was able to identify active services and understand their role within the system.

The exercise demonstrated the importance of network reconnaissance in cybersecurity and highlighted how open ports contribute to a system's attack surface. Regular network scanning and service analysis are essential practices for maintaining a secure environment.

---

Repository Structure

Task1_Basic_Network_Scanning_Nmap/
│
├── README.md
├── nmap_scan_results.txt
└── screenshots/
    ├── 01_nmap_version.png
    ├── 02_nmap_scan_results.png
    └── 03_saved_scan_output.png

---

Author:

Ayinaparthi Rohith
Oasis Infobyte Security Analyst Intern

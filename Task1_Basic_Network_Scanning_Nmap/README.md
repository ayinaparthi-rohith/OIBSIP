# Task 1 - Basic Network Scanning with Nmap

## Overview

As part of my Cybersecurity Internship at Oasis Infobyte, I performed a basic network scan using Nmap to identify open ports and services running on my local machine.
Network scanning is one of the first steps in security assessment because it helps identify which services are accessible and may potentially become attack points if not properly secured.

## Objective

The main objective of this task was to:
* Learn how to use Nmap for network reconnaissance.
* Identify open ports on a system.
* Detect services running on those ports.
* Analyze the security implications of the discovered services.

## Tool Used

* Nmap 7.99
* Windows 11 Pro
* Command Prompt

## Scan Performed

To identify running services and open ports, I executed the following command:

```bash
nmap -sV localhost
```

The `-sV` option enables service version detection, allowing Nmap to identify the services running behind open ports.

## Scan Results

The scan was performed on my local machine (localhost). Nmap identified the following open ports and services:

| Port | Service        | Description                          |
| ---- | -------------- | ------------------------------------ |
| 80   | HTTP           | Microsoft HTTP API service           |
| 135  | MSRPC          | Microsoft Remote Procedure Call      |
| 445  | Microsoft-DS   | SMB file and printer sharing service |
| 1433 | MS-SQL-S       | Microsoft SQL Server                 |
| 1434 | MS-SQL-S       | SQL Server Browser Service           |
| 2383 | MS-OLAP4       | SQL Server Analysis Services         |
| 7070 | SSL/RealServer | SSL-enabled service                  |

## Analysis

### Port 80 - HTTP

This port is commonly used for web services. The scan detected Microsoft's HTTP API service running on the system. Any web service exposed on a network should be monitored and updated regularly to reduce security risks.

### Port 135 - MSRPC

This service is used internally by Windows for communication between applications and services. Although necessary for many Windows functions, it should not be unnecessarily exposed to untrusted networks.

### Port 445 - SMB

Port 445 is used for file and printer sharing in Windows environments. Since SMB has been targeted in several major cyberattacks, it is important to secure and monitor this service.

### Ports 1433 and 1434 - SQL Server

These ports indicate that Microsoft SQL Server services are active on the system. Database services often store important information, making proper authentication and access control essential.

### Port 2383

This port is associated with Microsoft SQL Server Analysis Services, which is used for data analysis and reporting functions.

### Port 7070

Nmap detected an SSL-enabled service on this port. Additional investigation would be required to determine its exact purpose and whether it is required for normal system operations.

## Security Recommendations

Based on the scan results, I would recommend the following:
* Disable services that are not required.
* Keep Windows and installed applications updated.
* Restrict access to SMB services where possible.
* Use strong authentication for SQL Server instances.
* Regularly monitor open ports and network services.
* Configure firewall rules to limit unnecessary exposure.

## What I Learned

Through this task, I gained practical experience in:
* Installing and using Nmap.
* Performing basic network reconnaissance.
* Identifying open ports and active services.
* Understanding the purpose of common Windows network services.
* Analyzing potential security risks associated with exposed services.

## Conclusion

This task provided a practical introduction to network scanning and service enumeration using Nmap. The scan successfully identified several active services running on my system, including web, file-sharing, and database-related services.
Performing regular scans helps security professionals understand the attack surface of a system and identify services that may require additional security controls. This exercise improved my understanding of basic network security assessment techniques and the importance of monitoring exposed services.

## Author

Ayinaparthi Rohith
Cybersecurity Intern
Oasis Infobyte


# Task 10: Network Security Assessment Using Nmap and Wireshark

## Objective

The objective of this task was to perform a basic network security assessment on a local system by identifying active network services, analyzing network traffic, evaluating potential security risks, and providing recommendations to improve the security posture of the system.

The assessment was conducted using Nmap for network reconnaissance and Wireshark for packet analysis. The information collected from both tools was used to understand how the system communicates over the network and to identify services that may require additional security controls.

---

# What is a Network Security Assessment?

A Network Security Assessment is the process of examining a network and its services to identify security weaknesses, exposed services, misconfigurations, and potential attack vectors.

Organizations regularly perform security assessments to understand:

* Which services are running on their systems
* Which ports are accessible through the network
* How devices communicate with external systems
* What risks may exist within the environment
* What improvements can be made to strengthen security

The purpose of such an assessment is not to attack the system, but to understand its security condition and identify areas that may require attention.

---

# Assessment Environment

The assessment was performed on a Windows 11 system connected to a local network.

### Tools Used

#### Nmap

Nmap (Network Mapper) is an open-source network scanning tool used to discover hosts, identify open ports, and determine which services are running on a system.

For security professionals, Nmap is often the first step in understanding the attack surface of a network.

#### Wireshark

Wireshark is a network protocol analyzer that captures and displays network traffic in real time.

It allows security analysts to inspect packets, analyze communication patterns, identify protocols, and understand how information travels between systems.

---

# Phase 1: Network Reconnaissance Using Nmap

The first stage of the assessment involved performing a network scan to identify services running on the local machine.

The scan revealed several open ports and active services.

### Open Ports Identified

| Port | Service              |
| ---- | -------------------- |
| 80   | HTTP                 |
| 135  | Microsoft RPC        |
| 445  | SMB File Sharing     |
| 1433 | Microsoft SQL Server |
| 1434 | SQL Server Browser   |
| 2383 | Analysis Services    |
| 7070 | SSL Service          |

The presence of these ports indicates that multiple services are available through the network and can potentially accept incoming connections.

---

# Understanding the Scan Results

## Port 80 – HTTP Service

Port 80 is commonly used for web communication.

The presence of this port indicates that a web-based service is running on the system.

### Why This Matters

HTTP traffic is not encrypted. Information transmitted through HTTP can potentially be viewed by anyone monitoring the communication channel.

### Security Consideration

If sensitive information is transmitted using HTTP, attackers may be able to intercept that data.

### Recommendation

Use HTTPS whenever possible to ensure encrypted communication.

---

## Port 445 – SMB Service

Port 445 is used by the Server Message Block (SMB) protocol, which allows systems to share files and resources across a network.

### Why This Matters

SMB is commonly used within Windows environments. However, it has historically been targeted by several major cyberattacks.

### Security Consideration

If SMB is exposed unnecessarily, attackers may attempt unauthorized access or exploit known vulnerabilities.

### Recommendation

Restrict SMB access and disable the service if file sharing is not required.

---

## Port 1433 and 1434 – Microsoft SQL Server

These ports indicate that Microsoft SQL Server services are available on the system.

### Why This Matters

Databases often contain important organizational or application data.

### Security Consideration

Poorly secured databases can become targets for brute-force attacks, unauthorized access attempts, and data theft.

### Recommendation

Implement strong authentication, restrict access to trusted systems, and regularly review database security settings.

---

## Port 7070 – Additional Service

Port 7070 was also identified as active during the scan.

### Why This Matters

Any exposed service increases the overall attack surface of a system.

### Security Consideration

If the purpose of the service is unknown or unnecessary, it may create avoidable security risks.

### Recommendation

Verify the service configuration and disable it if it is not required.

---

# Phase 2: Network Traffic Analysis Using Wireshark

The second phase of the assessment focused on analyzing live network traffic.

Wireshark was used to capture packets while browsing websites and interacting with online resources.

To simplify the analysis, the captured traffic was filtered using:

```text
http
```

This filter displayed only HTTP-related communication.

---

# Traffic Analysis Findings

The captured traffic showed communication between the local system and external web servers.

The following information was observed:

| Field                  | Value           |
| ---------------------- | --------------- |
| Source IP Address      | 192.168.1.5     |
| Destination IP Address | 34.223.124.45   |
| Protocol               | HTTP            |
| Request Method         | GET             |
| Response Status        | HTTP/1.1 200 OK |

---

# Understanding the Captured Communication

The captured packet represents a request sent from the local machine to a web server.

The GET request indicates that the client requested information from the server.

The HTTP 200 OK response confirms that the server successfully processed the request and returned the requested resource.

This interaction demonstrates the basic communication process that occurs whenever a user accesses a website.

---

# Security Observations from Packet Analysis

One important observation during packet analysis was the visibility of HTTP traffic.

Because HTTP communication is not encrypted, information such as requested resources and communication details can be viewed directly within captured packets.

Although the captured traffic did not contain sensitive information, this demonstrates why modern websites typically use HTTPS instead of HTTP.

HTTPS encrypts communication and significantly reduces the risk of information interception.

---

# Overall Risk Assessment

Based on the assessment findings, the following areas require attention:

### Medium Risk

* HTTP communication observed during packet analysis.
* Additional exposed network services.

### High Risk

* SMB service exposure.
* Database services accessible through the network.

These findings do not necessarily indicate active vulnerabilities but represent areas that should be reviewed and secured appropriately.

---

# Recommendations

Based on the results of the assessment, the following recommendations are provided:

1. Use HTTPS for all web-based communication whenever possible.
2. Review and restrict SMB access.
3. Secure database services using strong authentication mechanisms.
4. Disable unnecessary services and ports.
5. Regularly review firewall rules.
6. Conduct periodic network scans to identify newly exposed services.
7. Monitor network traffic for unusual activity.
8. Keep operating systems and applications updated with the latest security patches.

---

# Files Included

Task10_Network_Security_Assessment/

├── README.md

├── network_security_assessment.md

├── nmap_results.txt

├── wireshark_capture.pcapng

└── screenshots/

---

# Conclusion

This assessment demonstrated how network reconnaissance and packet analysis can be used together to evaluate the security posture of a system.

Using Nmap, active services and open ports were identified. Using Wireshark, network communication was captured and analyzed. The combined findings provided valuable insight into the network exposure of the system and highlighted areas where security improvements could be implemented.

This task helped develop practical skills in network scanning, traffic analysis, risk identification, and security reporting, all of which are essential responsibilities of a Security Analyst.

## Author

Ayinaparthi Rohith

Security Analyst Intern

Oasis Infobyte

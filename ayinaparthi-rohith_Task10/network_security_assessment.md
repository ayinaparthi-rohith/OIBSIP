# Network Security Assessment Report

## Task Information

**Task Name:** Network Security Assessment
**Internship:** Oasis Infobyte Security Analyst Internship
**Tools Used:** Nmap, Wireshark, Windows Command Prompt

---

# 1. Introduction

The purpose of this network security assessment was to evaluate the security posture of a local network using Nmap and Wireshark. The assessment focused on identifying active devices, open ports, running services, and network traffic patterns that could potentially expose the network to security risks.

Network security assessments help organizations identify vulnerabilities, improve defenses, and reduce the chances of unauthorized access or cyberattacks.

---

# 2. Objectives

The primary objectives of this assessment were:

* Identify active hosts on the local network.
* Detect open ports and running services.
* Monitor network traffic activity.
* Analyze network communication patterns.
* Identify potential security vulnerabilities.
* Recommend security improvements.

---

# 3. Tools Used

| Tool                   | Purpose                              |
| ---------------------- | ------------------------------------ |
| Nmap                   | Network discovery and port scanning  |
| Wireshark              | Network traffic capture and analysis |
| Windows Command Prompt | Executing scan commands              |

---

# 4. Methodology

## Step 1: Network Identification

The local network information was obtained using the following command:

```bash
ipconfig
```

The IPv4 address was identified and the corresponding network range was determined for scanning.

---

## Step 2: Network Scanning with Nmap

The following Nmap command was executed:

```bash
nmap -sV 192.168.1.0/24 -oN nmap_results.txt
```

### Purpose

* Discover active devices.
* Identify open ports.
* Detect running services and versions.
* Gather information about network exposure.

The scan results were saved in:

```text
nmap_results.txt
```

---

## Step 3: Traffic Capture Using Wireshark

Wireshark was used to capture live network traffic while normal internet activity was performed.

Activities included:

* Web browsing
* DNS lookups
* HTTPS communication

The captured traffic was saved as:

```text
wireshark_capture.pcap
```

---

# 5. Findings

## Nmap Scan Results

The network scan identified active hosts and open ports.

Example open ports observed:

| Port | Service | Description              |
| ---- | ------- | ------------------------ |
| 80   | HTTP    | Web Service              |
| 443  | HTTPS   | Secure Web Service       |
| 5357 | WSDAPI  | Device Discovery Service |

### Observations

* Multiple services were accessible through open ports.
* Some ports were associated with device discovery services.
* Open services increase the attack surface if not properly secured.

---

## Wireshark Traffic Analysis

The packet capture revealed various types of network traffic.

### DNS Traffic

DNS packets were observed resolving domain names into IP addresses.

Example:

```text
google.com → IP Address
```

### HTTPS Traffic

Encrypted HTTPS communication was detected.

This indicates secure communication between devices and websites.

### ARP Requests

ARP packets were observed for local device discovery and address resolution.

### ICMP Packets

ICMP traffic was observed during network communication and connectivity checks.

---

# 6. Vulnerability Analysis

## Vulnerability 1: Open Services

### Description

Open ports expose services to the network and may be targeted by attackers.

### Risk Level

Medium

### Impact

Unauthorized users may attempt to exploit vulnerable services.

---

## Vulnerability 2: Device Discovery Services

### Description

Services such as WSDAPI allow device discovery on the network.

### Risk Level

Medium

### Impact

Attackers may gather information about connected devices.

---

## Vulnerability 3: Unnecessary Open Ports

### Description

Unused or unnecessary services increase the attack surface.

### Risk Level

Low to Medium

### Impact

Additional entry points may become available to attackers.

---

# 7. Risk Assessment

| Finding                   | Risk Level |
| ------------------------- | ---------- |
| Open Ports                | Medium     |
| Device Discovery Services | Medium     |
| Unnecessary Services      | Medium     |
| DNS Traffic Exposure      | Low        |
| HTTPS Communication       | Low        |

---

# 8. Security Recommendations

The following recommendations are suggested to improve network security:

1. Disable unused network services.
2. Close unnecessary open ports.
3. Enable and properly configure firewalls.
4. Use HTTPS instead of HTTP whenever possible.
5. Apply security patches and software updates regularly.
6. Monitor network traffic periodically.
7. Restrict device discovery services when not required.
8. Use strong passwords and authentication mechanisms.
9. Conduct regular vulnerability assessments.
10. Maintain proper network access controls.

---

# 9. Conclusion

The network security assessment successfully identified active devices, open ports, running services, and network communication patterns. The analysis revealed several areas where security can be strengthened, particularly through service management, firewall configuration, and continuous monitoring.

The use of Nmap and Wireshark proved effective for understanding network exposure and identifying potential security concerns. Implementing the recommended security measures will help reduce risks and improve the overall security posture of the network.

---

# Files Submitted

* network_security_assessment.md
* nmap_results.txt
* wireshark_capture.pcap
* Screenshots of Nmap Scan
* Screenshots of Wireshark Traffic Analysis
* README.md

---

# Outcome

Successfully performed a network security assessment using Nmap and Wireshark, analyzed network traffic and exposed services, identified potential security risks, and documented findings along with recommendations for improving network security.


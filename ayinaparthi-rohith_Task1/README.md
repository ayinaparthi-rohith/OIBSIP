# Task 1: Basic Network Scanning with Nmap

## Objective

The objective of this task was to perform a network scan using Nmap to identify open ports and running services on a local machine. The task also involved analyzing the discovered services and understanding their significance from a security perspective.


## Tools Used

* Nmap 7.99
* Windows 11 Pro
* Command Prompt (CMD)

---

## Task Execution

### Step 1: Install Nmap

Nmap was downloaded and installed successfully on the system.

### Step 2: Verify Installation

The following command was executed to verify that Nmap was installed correctly:

```bash
>> nmap --version
```

### Step 3: Perform Network Scan

A service version detection scan was performed on the local machine using the following command:

```bash
>> nmap -sV localhost
```

The `-sV` option enables service detection and attempts to identify the services running on open ports.

### Step 4: Save Scan Results

The output of the scan was saved into a text file named:

```text
>> nmap_scan_results.txt
```



## Scan Results

The scan successfully identified the following open ports and services on the local machine:

| Port | Service        | Description                             |
| ---- | -------------- | --------------------------------------- |
| 80   | HTTP           | Microsoft HTTP API service              |
| 135  | MSRPC          | Microsoft Remote Procedure Call service |
| 445  | Microsoft-DS   | SMB file and printer sharing service    |
| 1433 | MS-SQL-S       | Microsoft SQL Server database service   |
| 1434 | MS-SQL-S       | SQL Server Browser service              |
| 2383 | MS-OLAP4       | SQL Server Analysis Services            |
| 7070 | SSL/RealServer | SSL-enabled service                     |



## Analysis of Findings

### Port 80 (HTTP)

Port 80 is commonly used for web communication. The scan detected Microsoft's HTTP API service, indicating that a web-related service is active on the system.

### Port 135 (MSRPC)

This port is associated with Microsoft's Remote Procedure Call service, which enables communication between Windows applications and system components.

### Port 445 (SMB)

Port 445 is used for file and printer sharing through the SMB protocol. This service is important in Windows environments but should be monitored and secured properly because it is commonly targeted in network attacks.

### Port 1433 (Microsoft SQL Server)

This is the default port used by Microsoft SQL Server. Its presence indicates that SQL Server services are installed and running on the system.

### Port 1434 (SQL Server Browser)

This service helps clients locate SQL Server instances and supports database connectivity.

### Port 2383 (SQL Server Analysis Services)

This port is associated with SQL Server Analysis Services, which are commonly used for data analysis and reporting functions.

### Port 7070

An SSL-enabled service was detected on this port. Additional investigation would be required to determine the exact application using this service.



## Key Observations

* The target machine was active and reachable.
* Seven open TCP ports were identified.
* Multiple Microsoft SQL Server services were running on the system.
* SMB file-sharing services were enabled.
* A web service was active on port 80.
* An SSL-protected service was detected on port 7070.



## Learning Outcomes

Through this task, I gained practical experience in:

* Installing and using Nmap
* Performing basic network reconnaissance
* Identifying open ports and running services
* Understanding the purpose of commonly used Windows services
* Analyzing network scan results
* Documenting findings in a structured manner

---

## Files Included

```text
Task1_Basic_Network_Scanning_Nmap/
│
├── README.md
├── nmap_scan_results.txt
└── screenshots/
    ├── nmap_version.png
    ├── nmap_scan_results.png
    └── saved_scan_output.png


## Conclusion

This task successfully demonstrated the use of Nmap for network scanning and service identification. The scan helped identify active services running on the local machine and provided insight into how network reconnaissance is performed during a basic security assessment. The exercise improved my understanding of open ports, service detection, and the importance of regularly monitoring exposed services.



### Author

**Ayinaparthi Rohith**
Security Analyst Intern

Oasis Infobyte

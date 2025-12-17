Wireshark Traffic Analysis & Network Security Lab


This repository contains comprehensive guides, packet analysis findings, and detection techniques for various network activities and security anomalies using Wireshark.

📋 Table of Contents
Nmap Scan Identification

Man-In-The-Middle (MITM) & ARP Analysis

Protocol Analysis

Detection Filters & Notes

Exercise Case Studies

🔍 Nmap Scan Identification
Detailed methods for identifying common Nmap scan types through traffic patterns:


TCP Connect Scans (-sT): Relies on the full three-way handshake. These are typically conducted by non-privileged users and often feature window sizes larger than 1024 bytes.



SYN Scans (-sS): Stealthier scans that do not complete the three-way handshake. These are used by privileged users and generally have packet sizes ≤ 1024 bytes.


UDP Scans (-sU): Scans that do not require a handshake. Open ports may not prompt a response, while closed ports often return an ICMP "Destination Unreachable" message.

🛡️ Man-In-The-Middle (MITM) & ARP Analysis
This section covers the detection of ARP Poisoning/Spoofing attacks.

Key ARP Vulnerabilities
Lack of an authentication function.


Non-routable and insecure by design.

Susceptibility to gratuitous packets and zero-MAC destination tricks.


Attack Pattern Case Study
In our analysis of Exercise.pcapng, we identified a MITM attack where:


The Attacker: Host with MAC address ending in b4 (IP 192.168.1.25).



The Victim: Host with IP 192.168.1.12.


The Anomaly: The attacker crafted 284 ARP requests and successfully sniffed 90 username/password entries.

📡 Protocol Analysis
The repository includes analysis guides for various network protocols:


Host Identification: DHCP, NetBIOS, and Kerberos analysis.


Tunneling Traffic: Detecting ICMP and DNS tunneling.


Cleartext Protocols: Security risks associated with FTP and HTTP.


User Agent Analysis: Spotting anomalies in HTTP traffic to detect sophisticated adversaries.


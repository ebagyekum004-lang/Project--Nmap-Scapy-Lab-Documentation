# Project--Nmap-Scapy-Lab-Documentation

This repository contains documentation and findings from a controlled network reconnaissance exercise performed on an internal network using Nmap and Scapy tools. The lab focuses on practicing network scanning, service enumeration, and packet analysis using industry-standard tools. 
The documentation also contains screenshots from the lab environment.

**Objectives:**
The purpose of this lab is to demonstrate and practice fundamental network reconnaissance techniques including:
- Network scanning and host discovery.
- Operating system fingerprinting.
- Service and version identification.
- SMB enumeration and access testing.
- Packet sniffing and analysis.

These skills are foundational in ethical hacking and penetration testing engagements.

**Lab Environment:**
Machine: Kali Linux

Network: 10.6.6.0/24

Target System: 10.6.6.23


**Tools Used:**
Nmap:Network discovery and security auditing

Scapy: Packet crafting and manipulation

**NMAP LAB**

**Methodology & Results**
1. Host Discovery (Ping Sweep)
  
Command: nmap -sn 10.6.6.0/24

Purpose: Identify live hosts on the network.

Result: Target system `10.6.6.23` was detected as UP.

2. OS Detection
Command: sudo nmap -O 10.6.6.23

Purpose: Attempt to determine the operating system of the target.

Result: Nmap returned an OS guess based on TCP/IP fingerprinting techniques.

3. Service & Version Detection (FTP)
Command: nmap -p21 -sV -A -T4 10.6.6.23

Purpose: Identify services and versions running on port 21 (FTP).

Result: FTP service and specific version details were discovered, which can be used for vulnerability assessment.

4. SMB Enumeration (Port 445)
Command: nmap --script smb-enum-shares.nse -p445 10.6.6.23

Purpose: List SMB shares and check access permissions.

Result: SMB shares were listed along with their permission levels, identifying potential access points.

5. Manual SMB Access Test
Command: smbclient //10.6.6.23/print$ -N

Purpose: Test anonymous SMB login to identify misconfigurations.

Result: Anonymous login was successful, indicating a potential security misconfiguration that could allow unauthorized access to network resources.

**Conclusion:**
The lab exercises successfully demonstrated core network reconnaissance techniques. Key findings include:
1. Successful identification of a live host (`10.6.6.23`) on the network
2. OS fingerprinting capabilities using Nmap
3. Service enumeration revealing an FTP server
4. SMB share enumeration with permission information
5. Critical security misconfiguration allowing anonymous SMB access

These techniques form the foundation of information gathering in penetration testing and provide valuable information for vulnerability assessment and exploitation phases. 

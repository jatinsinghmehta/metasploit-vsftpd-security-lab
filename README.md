# metasploit-vsftpd-security-lab
Cybersecurity project demonstrating vulnerability assessment and controlled exploitation of vsFTPd 2.3.4 using Metasploit in an isolated virtual lab.
# Metasploit-Based Vulnerability Assessment & Exploitation

Project Overview
----------------

This project demonstrates a controlled cybersecurity vulnerability assessment and exploitation process using the Metasploit Framework in an isolated virtual lab environment.

The project focuses on the **vsFTPd 2.3.4 Backdoor Vulnerability (CVE-2011-2523)** using an intentionally vulnerable **Metasploitable 2** virtual machine as the target.

All testing was performed in an isolated **VirtualBox Host-Only network** for educational purposes.

Objectives
----------

- Identify a vulnerable FTP service
- Identify the vsFTPd 2.3.4 vulnerability
- Configure the appropriate Metasploit exploit module
- Perform controlled exploitation
- Establish a Meterpreter session
- Verify the obtained access and system information
- Perform basic post-exploitation enumeration
- Analyze security impact and risk
- Understand detection and remediation techniques

Lab Environment
---------------

| Component | Details |
|---|---|
| Attacker Machine | Kali Linux |
| Attacker IP | `192.168.56.102` |
| Target Machine | Metasploitable 2 |
| Target IP | `192.168.56.101` |
| FTP Service | vsFTPd 2.3.4 |
| FTP Port | `21/tcp` |
| Framework | Metasploit |
| Network | VirtualBox Host-Only |
| Vulnerability | vsFTPd 2.3.4 Backdoor |
| CVE | CVE-2011-2523 |

Tools Used
----------

- Kali Linux
- Metasploitable 2
- Oracle VirtualBox
- Nmap
- Metasploit Framework
- Meterpreter

Vulnerability Identification
----------------------------

Nmap was used to identify open ports and running services on the target.

The scan identified:

`21/tcp open ftp vsftpd 2.3.4`

The identified service was associated with the **vsFTPd 2.3.4 Backdoor Vulnerability (CVE-2011-2523)**.

Based on this information, the corresponding Metasploit module was selected for controlled exploitation.

Metasploit Exploitation
-----------------------

The following Metasploit module was used in the controlled lab:

`exploit/unix/ftp/vsftpd_234_backdoor`

Target configuration:

`RHOSTS = 192.168.56.101`

`RPORT = 21`

The exploit was successfully executed against the intentionally vulnerable target, resulting in a Meterpreter session.

Meterpreter Verification
------------------------

After establishing the Meterpreter session, basic system information was verified.

The session showed:

- **User:** root
- **Operating System:** Ubuntu 8.04
- **Architecture:** i686

Basic enumeration commands included:

`getuid`

`sysinfo`

`ipconfig`

`pwd`

`ls`

These commands were used to verify access, system information, network configuration, and file-system contents.

Post-Exploitation Enumeration
-----------------------------

Basic post-exploitation enumeration was performed to understand the level of access obtained.

The following information was collected:

- Network configuration
- Current working directory
- File-system contents
- Basic system information

The objective was assessment and verification within the controlled lab environment.

Impact & Risk Analysis
----------------------

Successful exploitation of the vulnerable service can lead to unauthorized high-privilege access.

### Confidentiality

- Unauthorized access to system files and information
- Potential exposure of sensitive data

### Integrity

- Unauthorized modification of files or configurations
- Unauthorized commands may affect system state

### Availability

- Potential disruption of services
- Misuse of system resources

**Risk Level: HIGH**

Detection & Remediation
-----------------------

### Detection

- Monitor FTP service activity and logs
- Detect unusual network connections
- Monitor unexpected processes and files
- Perform regular vulnerability scanning

### Remediation

- Upgrade or remove vsFTPd 2.3.4
- Disable unnecessary FTP services
- Restrict FTP access using firewall rules
- Apply least-privilege security controls
- Keep systems and services regularly patched

### Best Defense

**Patch vulnerable software + reduce unnecessary service exposure + continuous monitoring**

Attack Methodology / Workflow
------------------------------

The assessment followed a structured vulnerability exploitation workflow:

**Lab Setup → Network Verification → Vulnerability Identification → Exploit Configuration → Exploitation → Meterpreter Verification → Post-Exploitation Enumeration → Risk Analysis → Remediation → Reassessment**

Conclusion
----------

This project demonstrated a complete vulnerability assessment and controlled exploitation workflow using Metasploit.

The vsFTPd 2.3.4 vulnerability was identified and successfully exploited in an isolated virtual environment. A Meterpreter session was established, access was verified, and basic post-exploitation enumeration was performed.

The project also examined the potential security impact and appropriate detection and remediation techniques.

**Key Takeaway:**

**Identify vulnerabilities → Validate risk → Remediate → Reassess**

Disclaimer
----------

This project was conducted exclusively in an isolated and intentionally vulnerable virtual lab environment for educational and cybersecurity learning purposes.

Do not use these techniques against systems, networks, or services without explicit authorization.

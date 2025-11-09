# Detection-Lab
A simulated TCP Reverse Shell attack and SOC Analyst response. 

In the first half of the simulation, I create a TCP reverse shell virus.  Next, I enacted a social engineering phishing attack where an end user downloads the infected file, notices strange behavior, and creates a ticket to tech support.  In the second part, a SOC Analyst performs digital forensic analysis on the network, quarantines the virus, and escalates the ticket to a SOC Manager; using best practices from the organizaions playbooks. 

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Vitual machines running Windows 10 (Enduser) and Kali (attacker and SOC analyst) -- VirtualBox
- Command Line Lnterface for Red Team, virus creation, attack, and Blue Team, defense response -- Powershell, Bash, Python
- Network detection and virus payload deployment -- nMap and Metasploit
- Security Information and Event Management (SIEM) system for log ingestion and analysis -- Sysmon and Splunk 
- Network analysis tools for capturing and examining network traffic. -- Wireshark
- Telemetry generation tools to create realistic network traffic and attack scenarios. -- Sysmon and Splunk

## Steps

Part 1 - Red Team Attack
1. Create an Internal Network using VirtualBox and configure Sysmon, Splunk, Wireshark
2. Create a Metasploit TCP reverse shell virus file named Resume.PDF.exe
3. Initiate social engineering phishing attack with an email to HR Rep
4. Use msfConsole to intitate reverse shell and take command of target device

Part 2 - Blueteam response 
1. Analyze Wireshark packet capture and Splunk logs
2. Quarantine and elimiante the virus
3. Create a report for escalation and suggestions for further mitiation

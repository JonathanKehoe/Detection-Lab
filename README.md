# Detection-Lab
A simulated Reverse TCP Shell attack and SOC Analyst response. 

In the first half of the simulation, I created a reverse TCP shell virus.  Next, I enacted a social engineering phishing attack where an end user downloaded the infected file.  In the second part, a SOC Analyst performs digital forensic analysis on the network, quarantines the virus, and escalates the ticket to a SOC Manager, using best practices from the organization's playbooks. 

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Virtual machines running Windows 10 (Enduser) and Kali (attacker and SOC analyst) -- VirtualBox
- Command Line Interface for Red Team, virus creation, attack, and Blue Team, defense response -- Powershell, Bash, Python
- Network detection and virus payload deployment -- Nmap and Metasploit
- Security Information and Event Management (SIEM) system for log ingestion and analysis -- Sysmon and Splunk 
- Network analysis tools for capturing and examining network traffic. -- Wireshark
- Telemetry generation tools to create realistic network traffic and attack scenarios. -- Sysmon and Splunk

## Steps

Part 1 - Red Team Attack
1. Create an Internal Network using VirtualBox and configure Target Device with Sysmon, Splunk, Wireshark
2. Run an NMap scan against target machine and create a Metasploit TCP reverse shell virus file named Resume.PDF.exe
   ![Kali Attack Machine: Scan Target Device](NMap_scan.png "Scan the Target Machine with NMap to Find Open Ports")
   ![Kali Attack Machine: Run MSFConsole and the Exploit Handler](Run_MSFConsole_and_Exploit_handler.png "Kali Attack Machine: Run MSFConsole and the Exploit Handler")
   ![Kali Attack Machine: Configure Payload](Configure_Payload.png "Kali Attack Machine: Configure Payload of the Reverse Shell")
   ![Kali Attack Machine: Configure Listen Host](Configure_Listen_Host.png "Kali Attack Machine: Configure the Listen Host of the Attack Machine")
3. Host the Resume.pdf.exe and run msfConsole to initiate reverse shell
   ![Kali Attack Machine: Host Resume File](Host_Resume_File_downloaded_by_User.png "Kali Attack Machine: Host the Resume File on a Server Accessable to the User")
   ![Kali Attack Machine: Run TCP Handler](Run_TCP_handler.png "Kali Attack Machine: Run the TCP Handler")

4. Initiate social engineering phishing attack (email to HR Rep) with link to Resume.pdf.exe
   ![Target Device: End User Downloads Virus](End_User_Downloads_Resume.png "End User Downloads Resume.pdf.exe Virus")
   ![Target Device: End User Opens Virus](End_User_Opens_Resume.png "End User Opens Resume.pdf.exe Virus")
   ![Kali Attack Machine: Virus Initiates Connection](Host_resume_file_opened_by_User.png "Resume.pdf.exe Initiates Connection")
   
6. Take command of target device, run basic commands to check status, and move laterally to obtain private files
   ![Kali Attack Machine: Intitiate Shell and Lateral Movement](TCP_Shell_Lateral_Local_Group_Net_User_and_IP.png "Initiate TCP Shell and Move laterally Through the Target System")

   
Part 2 - Blueteam Response 
1. Isolate end user device
2. Analyze Wireshark packet capture and Splunk logs
3. Remove infected files
4. Identify affected personal files
5. Identify changes made
6. Restore from backup
7. Create a report for escalation and suggestions for further mitigation

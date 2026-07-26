Author
Khabbab Sarker (innominate)

Date
26-07-2026

Objective
Scan the local network 192.168.80.0/24 and identify open ports and services to understand network exposure.

Environment
Kali Linux (VM)
Interface: eth0
Local IP: 192.168.80.128
Network: 192.168.80.0/24
Commands run
Discovery scan: sudo nmap -sS 192.168.80.0/24 -oN scan_results.txt

Targeted service & OS detection: sudo nmap -sV -O -p 135,139,445,2869,7070 192.168.80.1 -oN nmap_deep_192.168.80.1.txt

SMB enumeration (NSE): sudo nmap --script smb-enum-shares,smb-os-discovery,smb-security-mode -p 139,445 192.168.80.1 -oN nmap_smb_enum_192.168.80.1.txt

(Optional) Wireshark packet capture:

Filter used: tcp.port == 135 || tcp.port == 139 || tcp.port == 445 || tcp.port == 2869 || tcp.port == 7070
Save as scan_capture.pcap
Findings (summary)
Host 192.168.80.1 — ports open: 135, 139, 445, 2869, 7070.
Host 192.168.80.254 — filtered (no responding ports).
Host 192.168.80.128 (this machine) — all scanned ports closed.
Risk assessment
SMB ports (139, 445) and RPC (135) are high-risk: possible lateral movement, file-share exposure, and remote code execution vulnerabilities if unpatched.
UPnP (2869) can allow port mapping and info exposure.
7070 (streaming / vendor service) could contain vulnerabilities depending on version.
Mitigation steps recommended
Patch host at 192.168.80.1.
Disable SMBv1 and restrict SMB to trusted hosts.
Disable UPnP on gateway if not required.
Configure host firewall to block ports from WAN.
Close unused ports and apply least privilege to management interfaces.
Files included
scan_results.txt
nmap_deep_192.168.80.1.txt
nmap_smb_enum_192.168.80.1.txt
scan_capture.pcap
screenshots/
Notes
All scans were performed on devices in my local network / VMs (authorized testing).

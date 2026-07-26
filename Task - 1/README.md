# Task 1: Local Network Port Scan

## Objective
The goal of this task was to learn how to discover open ports on devices in my local network using Nmap.

## Tools Used
* **OS:** Kali Linux (in a VMware VM)
* **Scanning Tool:** Nmap

## Process
1.  I first identified my local network's IP range using the `ip a` command. My range was `192.168.140.0/24`.
2.  I then executed a TCP SYN scan with the command: `sudo nmap -sS 192.168.140.0/24 -oN results.txt`.
3.  The scan identified 4 active devices on the network.

## Findings & Risks
* **Device 1 (IP: 192.168.140.1):** This device has ports 135 (msrpc) and 2179 (vmrdp) open. Open `msrpc` ports can sometimes be a risk if the system is not patched, as they have been targeted by worms in the past.
* **Device 2 (IP: 192.168.140.2):** This device has port 53 (domain) open, indicating it is a DNS server. This is typical for a network router.

## Scan Results
The full scan output is available in the `results.txt` file in this repository.

## Screenshots
<img width="855" height="534" alt="Screenshot 2025-10-20 180505" src="https://github.com/user-attachments/assets/9f86b414-7042-4b48-b16f-58697e4b3bd1" />

<img width="555" height="526" alt="Screenshot 2025-10-20 180533" src="https://github.com/user-attachments/assets/20a0fb6b-a390-47f0-825b-c1b7b1f9dbf5" />

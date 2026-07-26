#  cybersecurity-internship-task-4

## [cite_start]Task 4: Setup and Use a Firewall on Windows/Linux [cite: 3]

[cite_start]This repository contains the deliverables for Task 4 of the Elevate Labs Cybersecurity Internship[cite: 2].

---

### 🎯 Objective

[cite_start]The objective of this task is to configure and test basic firewall rules on a Linux system using UFW (Uncomplicated Firewall) to allow or block specific network traffic[cite: 4].

### 🛠️ Tools Used

* **OS:** Kali Linux (or any Debian-based distribution)
* [cite_start]**Firewall:** UFW (Uncomplicated Firewall) [cite: 5]
* **Utility:** `netcat` (for testing port connectivity)

---

### 👣 Steps Executed

Below is a detailed walkthrough of the steps taken to configure and test the firewall.

#### 1. Check Initial Firewall Status

First, I checked the current status of UFW to see if it was active.

```bash
sudo ufw status

# Task 2: Phishing Email Analysis Report

## 1. Objective
The objective of this task was to analyze a sample email file (`.eml`) to identify its characteristics and determine if it was a phishing attempt.

## 2. Tools Used
* **Operating System:** Kali Linux
* **Terminal Commands:** `cd`, `ls`, `cat`
* **Sample Source:** A sample `.eml` file obtained from a public GitHub repository.
* **Sample Source Link** https://github.com/rf-peixoto/phishing_pot.

## 3. Process
1.  **Obtain Sample:** A safe phishing email sample (`sample-1.eml`) was downloaded.
2.  **Initial Triage:** The file was saved and accessed via the Kali Linux terminal.
3.  **Static Analysis:** The `cat` command was used to display the raw source of the email, including its headers and body.
4.  **Indicator Identification:** The headers and body were manually inspected for common phishing red flags.

## 4. Analysis & Findings
The email sample was conclusively identified as a phishing attempt based on the following indicators:

* **Header Analysis:**
    * **Failed Authentication:** The `Authentication-Results` header showed `spf=temperror`, `dkim=none`, and `dmarc=temperror`. This means the sender's server was not authorized to send emails on behalf of the domain it claimed to be from.
    * **Mismatched Sender Information:** The `From` header displayed the name of a bank, but the `Return-Path` pointed to a generic and unrelated server hostname (`root@ubuntu-s-1vcpu-1gb-35gb-intel-sfo3-06`).

* **Body Analysis:**
    * **Social Engineering:** The subject line, "Your card has 92,990 LIVELO points expiring today!", created a false sense of urgency to manipulate the user into acting quickly.
    * **Malicious Link:** The email body, encoded in Base64, contained a link pointing to a suspicious and non-official domain (`blog1seguimentmydomaine2bra[.]me`), not the legitimate bank's website.

## 5. Conclusion
The email is definitively malicious. It uses header forgery to spoof a trusted sender and social engineering tactics to lure the user into clicking a dangerous link. The technical evidence in the headers confirms the email's fraudulent nature.

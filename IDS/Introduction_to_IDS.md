## What is an Intrusion Detection System (IDS)?

An Intrusion Detection System (IDS) is a cybersecurity tool designed to monitor network or system activities and detect suspicious behaviors or known attack patterns. It acts as a watchdog by alerting security teams about potential threats.

### How It Works:
- Monitors incoming and outgoing network packets or system logs.
- Matches traffic patterns against known signatures or predefined rules.
- Alerts administrators in case of anomalies or malicious activities.

**Example**: Imagine your office has a door with a motion detector. The detector doesn’t block or stop people but alerts security when someone enters. Similarly, an IDS detects but does not block attacks.

## IDS vs. IPS (Intrusion Prevention System)

Though IDS and IPS are closely related, they differ in how they handle threats:

| **Feature**          | **IDS**                       | **IPS**                                        |
| -------------------- | ----------------------------- | ---------------------------------------------- |
| **Function**         | Monitors and detects threats. | Prevents and blocks malicious activity.        |
| **Traffic Handling** | Passive (doesn’t interfere).  | Active (can drop packets or block IPs).        |
| **Response**         | Alerts security teams.        | Takes immediate action (e.g., blocks traffic). |

**Example**:
- An IDS is like a CCTV camera that records and raises an alarm when it spots suspicious activity.
- An IPS is like a security guard who intervenes to stop the intruder.

## Types of IDS: Network-based IDS (NIDS) and Host-based IDS (HIDS)

There are two primary types of IDS:

### 1. **Network-based IDS (NIDS)**:
- Monitors traffic across an entire network segment.
- Placed at strategic points (e.g., between routers and switches).
- Best for detecting large-scale attacks like **DDoS** or malicious payloads in packets.
- **Example**: If a hacker tries to scan an organization's entire network using **Nmap**, a NIDS can detect the unusual traffic and raise an alert.  

### 2. **Host-based IDS (HIDS)**:
- Monitors activities on individual hosts (e.g., a server or endpoint).    
- Tracks file modifications, application logs, and system processes.    
- Best for detecting insider threats or malware on a specific machine.    
- **Example**: If ransomware modifies critical files on a server, a HIDS can detect the changes and alert the administrator.

## Role of IDS in detecting network security threats: Signature-based vs. anomaly-based detection

Intrusion Detection Systems can identify threats through two main detection methods:

### 1. **Signature-Based Detection**:
- Matches traffic against a database of known attack patterns or signatures.
- Works well for known threats (e.g., **SQL Injection**, **Buffer Overflow**).
- Fast and reliable but cannot detect new or unknown attacks.
- **Example**: A signature-based IDS detects a **Metasploit exploit** because its payload matches a predefined signature.

### 2. **Anomaly-Based Detection**:
- Establishes a baseline of normal network behavior.
- Flags deviations from the baseline as potential threats.
- Useful for detecting new or unknown threats but prone to false positives.
- **Example**: If a user suddenly starts uploading gigabytes of data to an external server, an anomaly-based IDS will flag it as suspicious.

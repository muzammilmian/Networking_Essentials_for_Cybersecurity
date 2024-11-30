# Difference Between TCP and UDP

In networking, TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are like two different delivery services. TCP is like a certified mail service, ensuring your package is delivered, while UDP is like regular mail—faster but without a delivery confirmation.

## Key Differences

| Feature         | TCP (Transmission Control Protocol)                                           | UDP (User Datagram Protocol)                                    |
| --------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Connection Type** | Connection-oriented (requires a handshake).                                   | Connectionless (no handshake required).                         |
| **Reliability**     | Reliable delivery with acknowledgment.                                        | Unreliable, no delivery confirmation.                           |
| **Speed**           | Slower due to error checking and retransmission.                              | Faster due to minimal overhead.                                 |
| **Error Checking**  | Performs error checking and retransmits lost packets.                         | Minimal error checking, packets may be lost.                    |
| **Use Case**        | Used for applications needing reliable delivery (e.g., email, file transfer). | Used for time-sensitive applications (e.g., streaming, gaming). |

---

# How TCP Establishes Connections (Three-Way Handshake Process)

Before data can be transmitted using TCP, a connection must be established between the sender and receiver. This process is called the **three-way handshake**, ensuring both parties are ready to communicate.

- **Step 1**: Client → Server: “Hey, are you there? (SYN)”
- **Step 2**: Server → Client: “Yes, I’m here. Are you ready? (SYN-ACK)”
- **Step 3**: Client → Server: “Yes, I’m ready. Let’s begin. (ACK)”

---

# Common Ports and Protocols

In the networking world, ports and protocols are like addresses and languages—each service has a specific port number and uses a protocol to communicate. Let’s explore some of the most common ones:

- **HTTP** (Port 80)
- **HTTPS** (Port 443)
- **FTP** (Ports 20 and 21)
- **SSH** (Port 22)
- **DNS** (Port 53)
- **SMTP** (Port 25)
- **RDP** (Port 3389)

---

# Network Attacks Targeting TCP/IP Protocols

TCP/IP is the backbone of internet communication, but it’s also a common target for cyberattacks.

### **SYN Flood Attack**

- **What It Is**: Exploits the TCP three-way handshake by sending a flood of SYN packets but not completing the handshake. This overwhelms the server, causing it to run out of resources.
- **Example**: Imagine hundreds of prank calls to a restaurant where no one places an order, leaving the staff too busy to handle real customers.
- **Prevention**: Implement **SYN cookies** and **rate-limiting** on your firewall.

---

### **Port Scanning**

- **What It Is**: Attackers scan a network to identify open ports and services. This helps them find vulnerabilities.
- **Example**: A burglar checking every door and window of a house to find an unlocked entry point.
- **Prevention**: Use **firewalls** to block unnecessary ports. Monitor scans with **intrusion detection systems (IDS)**.

---

### **DNS Spoofing**

- **What It Is**: Attackers tamper with DNS responses, redirecting users to malicious websites.
- **Example**: You type "www.bank.com," but due to spoofing, you’re redirected to a fake login page.
- **Prevention**: Use **DNSSEC** (Domain Name System Security Extensions).

---

### **Man-in-the-Middle (MITM) Attacks**

- **What It Is**: Intercepting communication between two devices to eavesdrop or modify data.
- **Example**: An attacker intercepting sensitive data on an unsecured HTTP connection.
- **Prevention**: Use encrypted protocols like **HTTPS** and **SSH**.

---

### **Brute Force on SSH (Port 22)**

- **What It Is**: Repeatedly guessing login credentials for an SSH server.
- **Example**: Attackers trying hundreds of password combinations until they find the correct one.
- **Prevention**: Use **strong, unique passwords** and **multi-factor authentication**. Restrict access by **IP** using firewalls.

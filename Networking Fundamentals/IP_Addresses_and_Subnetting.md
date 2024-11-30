# IP Addresses and Subnetting

## What is an IP Address?

An **IP address**, or **Internet Protocol address**, is like a digital home address for devices connected to a network, helping them identify and communicate with each other. Think of it as the address your favorite online store needs to deliver a package to your doorstep. Just like the store needs a unique address to deliver a package to the right home, computers and devices need unique IP addresses to send information to each other over the internet.

Every device connected to the internet—whether it’s your phone, laptop, gaming console, or even smart fridge—has an IP address. This address is a unique identifier that ensures information goes to and from the correct device. Without IP addresses, there would be no way to distinguish one device from another, causing a complete communication breakdown on the internet.

---

## Types of IP Addresses: IPv4 vs. IPv6

There are two main types of IP addresses: **IPv4** and **IPv6**. Let’s break these down:

### a) IPv4 Addresses
IPv4 is the older version and is the most widely used type of IP address today. IPv4 addresses look like a set of four numbers separated by dots, such as `192.168.1.1`. Each number in this address can range from 0 to 255, which gives IPv4 addresses a range of roughly 4.3 billion unique addresses.

#### Example of an IPv4 Address:
Imagine you live in a small neighborhood where each house has a unique address. Let’s say you live at **192 Baker Street**, and the house next door is **193 Baker Street**. The addresses are unique but limited to the houses in that neighborhood.

#### Key Points of IPv4:
- **Format**: Four numbers separated by dots (e.g., `192.168.1.1`).
- **Range**: About 4.3 billion unique addresses.
- **Limitation**: Limited number of addresses, not enough for all devices globally.

### b) IPv6 Addresses
IPv6 was created to solve the limitations of IPv4. It uses a much larger address space, with **128 bits** compared to IPv4’s **32 bits**. This allows for **340 undecillion** unique IP addresses—a number so vast it’s hard to imagine running out anytime soon!

#### Example of an IPv6 Address:
Imagine a city planner has unlimited space to assign addresses, so each home has an extremely unique, long address—something like `2001:0db8:85a3:0000:0000:8a2e:0370:7334`. With IPv6, each device can have a globally unique address without the risk of running out.

#### Key Points of IPv6:
- **Format**: Eight groups of four hexadecimal characters separated by colons (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
- **Range**: 340 undecillion unique addresses (3.4 x 10^38).
- **Benefit**: Virtually unlimited addresses, suitable for an ever-growing internet of devices.

---

## What is Subnetting?

**Subnetting** is the process of dividing a large network into smaller, more manageable segments, or **subnets**. Think of it as splitting a big room with many people into smaller sections based on activities or departments. Each group can operate more efficiently without disturbing the others, and security is also improved because access can be controlled within each segment.

---

## Why Subnetting Matters for Security

- **Isolates Traffic**: Subnetting keeps internal traffic within each subnet, preventing devices from accessing other parts of the network unless allowed.
- **Enhances Network Performance**: By reducing unnecessary data flow across the entire network, subnetting allows each segment to operate more efficiently, improving performance.
- **Controls Access and Minimizes Threats**: With subnetting, administrators can set different access levels for each subnet. For example, the IT department’s subnet may have access to sensitive areas of the network, while other departments are limited to their own subnet.
- **Improves Network Management**: Subnetting simplifies network management by breaking a complex network into smaller, more easily controlled pieces.

---

## Subnet Mask, CIDR Notation, and Creating Subnets

To implement subnetting, we need to understand a few important concepts: **Subnet Masks**, **CIDR Notation**, and how to **create subnets**.

### Subnet Mask
A **subnet mask** is a sequence of numbers that tells devices where to divide the network portion from the host portion of an IP address. Think of a subnet mask like a divider that separates the street name (network) from the house number (device) in an address. The subnet mask shows which “streets” (networks) are connected but have their own “houses” (devices) that can operate independently.

#### Example of a Subnet Mask:
A common subnet mask is `255.255.255.0`. Here, the first three sets of numbers (`255.255.255`) are used for the network portion, and the last set (`0`) is used for the device portion within that subnet.

---

### CIDR Notation
**CIDR (Classless Inter-Domain Routing)** notation is a way of simplifying the expression of subnet masks. Instead of writing out the full subnet mask (e.g., `255.255.255.0`), CIDR notation uses a “/” followed by a number that tells you how many bits are used for the network portion.

#### Example of CIDR Notation:
The subnet mask `255.255.255.0` can be written as `/24` because the first 24 bits are used for the network.

---

### Subnetting Examples

| **CIDR** | **Hosts Per Subnet** | **Subnet Mask** | **Example Notes**               |
| -------- | -------------------- | --------------- | ------------------------------- |
| **/1**   | 2,147,483,648        | 128.0.0.0       | Double hosts as CIDR decreases.   |
| **/2**   | 1,073,741,824        | 192.0.0.0       | Subtract 2 for network/broadcast. |
| **/3**   | 536,870,912          | 224.0.0.0       |                                 |
| **/4**   | 268,435,456          | 240.0.0.0       |                                 |
| **/5**   | 134,217,728          | 248.0.0.0       |                                 |
| **/6**   | 67,108,864           | 252.0.0.0       |                                 |
| **/7**   | 33,554,432           | 254.0.0.0       |                                 |
| **/8**   | 16,777,216           | 255.0.0.0       | Class A default subnet mask.    |

---

| **CIDR** | **Hosts Per Subnet** | **Subnet Mask** | **Usable Hosts** |
| -------- | -------------------- | --------------- | ---------------- |
| **/9**   | 8,388,608            | 255.128.0.0     | 8,388,606        |
| **/10**  | 4,194,304            | 255.192.0.0     | 4,194,302        |
| **/11**  | 2,097,152            | 255.224.0.0     | 2,097,150        |
| **/12**  | 1,048,576            | 255.240.0.0     | 1,048,574        |
| **/13**  | 524,288              | 255.248.0.0     | 524,286          |
| **/14**  | 262,144              | 255.252.0.0     | 262,142          |
| **/15**  | 131,072              | 255.254.0.0     | 131,070          |
| **/16**  | 65,536               | 255.255.0.0     | 65,534           |

---

#### Key Notes:
- **Hosts Calculation**: `2^(32 - CIDR)`
- **Subtract 2**: One for **network ID**, one for **broadcast**.
- **CIDR Doubling Rule**: Every decrease by 1 bit doubles the number of hosts.
- **Subnet Mask**: Represents which portion is **network** vs **host**.

---

#### Example Calculations:

**Example 1**: Calculate Hosts for `/20`

1. Formula: `2^(32−CIDR)`
   - `2^(32−20) = 2^12 = 4096`
2. Subtract 2 (for network ID and broadcast):  
   - `4096 - 2 = 4094`
   - **Usable Hosts = 4094**

**Example 2**: Determine the Subnet Mask for `/26`

1. CIDR `/26` means 26 bits are for the network, leaving `32 - 26 = 6` bits for hosts.
2. Subnet Mask: Start with all 255s, then convert the 6 bits to binary: 11111111.11111111.11111111.11000000 = **255.255.255.192** 

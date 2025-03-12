# Security-Assessment-of-Public-Wi-Fi-Networks.
📌 Context and Motivation

I have always been intrigued by how networks operate in public spaces such as libraries, airports, and cafes. One day, while studying in a library, I noticed that I couldn't see other devices on the network or capture useful information in Wireshark.

This led me to wonder: What security measures are in place, and how do they work?

I decided to analyze the network's security ethically and for educational purposes, documenting my findings to learn more about public network protection.

🔍 Methodology: Public Network Security Evaluation

1️⃣ Connectivity Verification
Checked my IP address with ip a and found that no IPv4 address was assigned.
Ran arp -a and found no other devices on the network.
Used netstat -rn and noticed there was no visible gateway.

2️⃣ Traffic Analysis with Wireshark
Captured packets on eth0 and found only discovery traffic (DHCP, ICMPv6).
No ARP traffic or responses from other devices, suggesting Client Isolation was enabled.

3️⃣ Attempt to Manually Obtain an IP Address
Tried sudo dhclient eth0, but no IP was assigned, indicating DHCP filtering.
Attempted to assign an IP manually, but there was no response to ping.

4️⃣ Possible Implemented Defenses

✔ Client Isolation to prevent Man-in-the-Middle (MITM) attacks.✔ MAC Address Filtering (only authorized devices receive an IP).✔ Firewall blocking ARP and DHCP Responses.

🛠 Tools Used

Wireshark: Network traffic capture and analysis.
Nmap: Scanning active hosts on a public network.
Macchanger: Analyzing MAC address filtering.
Tcpdump: Capturing traffic on network interfaces.

🛡️ How to Protect Public Networks Against Attacks

Public networks should implement security measures to prevent sniffing and spoofing attacks.Here are some effective defenses:

🔒 Client Isolation: Ensures that clients cannot communicate with each other.

🔥 DHCP Snooping: Prevents MITM attacks with rogue DHCP servers.

🚀 Exclusive Use of IPv6: Can make ARP Spoofing and MITM attacks on IPv4 more difficult.

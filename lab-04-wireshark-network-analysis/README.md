# 🧾 LAB 04 — Wireshark Network Traffic Analysis

## Objective
This lab explores how web traffic flows across a network by analyzing packet captures in Wireshark. 
The goal is to understand the full lifecycle of a web request from DNS resolution through TCP handshake to encrypted HTTPS communication.

---

## Tools Used
- Wireshark
- Kali Linux (VMware Fusion)
- Web browser (Firefox)
- Example website: `example.com`

---

## Network Concepts Demonstrated

### 1. DNS Resolution
The browser first resolves the domain name into an IP address using DNS.  
This step allows the system to locate the correct server on the internet.

**Key Observation:**
- `example.com` resolves to a Cloudflare edge IP (172.66.x.x), indicating CDN usage.

---

### 2. TCP Three-Way Handshake
Before any data is transmitted, a TCP connection is established:

- SYN (Client → Server)
- SYN-ACK (Server → Client)
- ACK (Client → Server)

This handshake confirms both sides are ready for communication.

---

### 3. TLS Encryption (HTTPS)
After the TCP connection is established, TLS negotiation begins.

- Client Hello
- Server Hello
- Encrypted Application Data

All application-layer data is encrypted and not readable in Wireshark without decryption keys.

---

### 4. Encrypted Traffic Observation
Using “Follow TCP Stream” shows encrypted binary data.  
This confirms that HTTPS protects application payloads from inspection.

---

## Key Findings

- Modern web traffic is heavily encrypted using TLS.
- DNS reveals the destination IP before encryption begins.
- TCP establishes reliable communication before data transfer.
- Most application content is not visible in packet captures due to encryption.
- CDNs (like Cloudflare) are commonly used for web delivery.

---

## Screenshots

### Packet Capture Overview
Shows overall traffic during the browsing session.

### TCP SYN Packet
Shows initiation of a TCP connection from client to server.

### TCP SYN-ACK Packet
Shows server response to connection request.

### Web Session / Encrypted Traffic
Shows TLS-protected communication in Wireshark.

---

## Conclusion

This lab demonstrates the foundational stages of web communication. Even though modern traffic is encrypted, network analysis still provides critical metadata including DNS resolution, connection establishment, and traffic patterns. These insights are essential for cybersecurity monitoring and incident response.

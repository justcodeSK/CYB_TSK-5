# Task 5 – Capture and Analyze Network Traffic Using Wireshark

## Objective
Capture live network packets and identify basic protocols and traffic types.

## Tools Used
- **Wireshark** (Free, open-source packet analyzer)
- Operating System: [Kali & Windows 11]

## Steps Followed
1. **Installed Wireshark**
   - Allow installation of Npcap (needed for packet capture).
   - Downloaded from [https://www.wireshark.org](https://www.wireshark.org) and installed successfully.
   - In kali Linux
     - `sudo apt update`
     - `sudo apt install wireshark`
     - `sudo usermod -aG wireshark $kali`
   
3. **Started Packet Capture**  
   - Selectedan active Network interface (used eth0-ethernet, Wifi, loopback for ping).
   - Started live capture.

4. **Generated Network Traffic**  
   - Opened multiple tabs in multiple web browser.
   - Performed `ping` using Guses OS1 and Guest OS2 which are connected in an internal network and configured ip address for connection, to generate ICMP packets.
     `ping 192.168.56.101`

5. **Stopped Capture**  
   - Have captured different Traffics :
     
     `django web-server localhst packets`
   
     `wifi traffic`
   
     `Hping3 dos flood attack traffic` etc.

7. **Filtered Packets**  
   - Used display filters :
     - `http` → HTTP traffic (Hypertext Transfer Protocol)
     - `dns` → DNS traffic (Domain Name System)
     - `tcp` → TCP packets (Transmission Control Protocol)

8. **Identified Protocols**  
   - Found different protocols in the capture:
     - ## 1. TCP (Transmission Control Protocol)
         - ***Connection-oriented*** transport layer protocol.
         - Ensures reliable, ordered, and error-checked delivery of data between applications over a network.
         - Uses **three-way handshake** (SYN, SYN-ACK, ACK) to establish a connection.
         - Guarantees data delivery and retransmits lost packets.
         - Supports flow control and congestion control.
         - In the OSI model, TCP Protocol operates at Layer 4, the Transport layer.
      - ## 2. ARP (Address Resolution Protocol)
         - ***Network layer*** utility protocol.
         -  Maps an IP address to its corresponding MAC (hardware) address in a local network.
         - Works only within a local area network (LAN).
         - Sends a broadcast query: "Who has this IP address?" and gets a MAC address in reply.
      - ## 3. SSL (Secure Sockets Layer)
         - ***Cryptographic protocol*** (deprecated, replaced by TLS).
         - Encrypts data transmitted over a network to ensure confidentiality, integrity, and authentication.
         - Uses asymmetric encryption for key exchange and symmetric encryption for data transfer.
         - Protects against eavesdropping and tampering.
      - ## 4. DNS (Domain Name System)
         - ***Application layer protocol***.
         -  Translates human-readable domain names.
           
              for eg ;
            
                      `example.com` into IP addresses like `93.184.216.34`.
            
         -  Supports query types like A (IPv4 address), AAAA (IPv6 address), MX (mail server).
         -  Hierarchical structure with root, TLD, and authoritative name servers. Refered - `https://youtu.be/x-ZWK-Uc76k?si=Nf61_k0NBZKBi3yb`.
      -  ## 5. ICMP (Internet Control Message Protocol)
         - ***Network layer protocol***.
         - Sends control messages for diagnostics and error reporting between network devices.
         - Commonly used by the `ping`.
         - Reports unreachable hosts, network congestion, or routing issues.

9. **Exported Capture**  
   - Saved as `network_capture.pcap`.
   - Saved as `django_webserver_capture.pcap`.
   - Saved as `ping .pcap`.

## Findings
- **HTTP packets** contained request and response headers.
- **DNS queries** showed domain lookups (e.g., for `google.com`).
- **TCP packets** included SYN, ACK, and FIN flags.
- Noticed some ICMP packets from the ping command.
- Learned about Hping3 used for Dos and Ddos attack.
- Learned to capture Network traffic Packets.

## Key Concepts Learned
- Packet structure and how to read it in Wireshark.
- Use of display filters to focus on specific protocols.
- TCP three-way handshake identification.

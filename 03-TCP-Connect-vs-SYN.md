# Task 06-09: TCP Connect Scan vs SYN Scan

## TCP 3-Way Handshake (Basic Rule)
This is the basic rule of TCP/IP. When 2 computers connect, 3 steps happen:
1. Client -> SYN -> Server
2. Server -> SYN-ACK -> Client
3. Client -> ACK -> Server

### 1. TCP Connect Scan (-sT)
```bash
nmap -sT MACHINE_IP -Pn
```
- Completes the full 3-way handshake.
- **Disadvantage:** Your IP is saved in the target's log file. The firewall becomes obvious.
- **Advantage:** Does not require sudo/root on Linux. It works with normal permission.
- **Speed:** Slow.

### 2. SYN Scan (-sS) - Industry Standard
```bash
sudo nmap MACHINE_IP -sS -Pn
```
- Also called **Half-Open Scan**.
- It does not complete the handshake. It stops after receiving SYN-ACK.
- **Advantage:** Stealthy (not logged), Fast, Most reliable.
- **This is the first scan you should always do** to check which doors (ports) are open.
- Requires sudo permission.

### 3. Firewall Case - What is Filtered?
If a firewall blocks the SYN packet, Nmap gets no response.
- When Nmap gets no response, it marks the port as **Filtered**.
- A log file is created on the target with our IP address if we do a full connect scan, which makes it obvious we scanned.
- For this reason, industry uses SYN scan as the standard.
- Ports have 3 states: Open, Closed, Filtered.
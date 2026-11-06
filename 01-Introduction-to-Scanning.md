# Task 01-02: Introduction to Nmap & Scanning

## Why Scanning Before Hacking?
Before any attack, full enumeration is required. You must know what services are running.

## What is a Port?
A port is a doorway for a service. When a computer runs a service like a website, it opens a port.
- A connection is always between two hosts.
- Example: Your computer opens a random port (e.g., 45261, 47523) to connect to a website's known port (e.g., 443 for HTTPS).
- So: `Random Local Port (45261) -> Remote Port (443)`

## Important Ports
- **80** = HTTP (Normal Website)
- **443** = HTTPS (Secure Website)
- **139** = NETBIOS
- **445** = SMB
- **Total Ports: 65535**

In CTF, always check these standard ports first. They give you the initial attack surface.
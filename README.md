# Nmap Notes - TryHackMe Further Nmap (Task 01 to 14)

> Documented from my handwritten notes. Original room: TryHackMe - Further Nmap
> Converted from Hinglish understanding to professional English for GitHub.

## Repository Structure

- **01-Introduction** - What is Scanning & Ports
- **02-Scan-Families** - NULL, FIN, Xmas Scans
- **03-TCP-Connect-vs-SYN** - 3-Way Handshake & Stealth
- **04-NSE-Scripts** - Nmap Scripting Engine
- **05-Toolbox-Search** - Script Categories & script.db
- **06-Firewall-Evasion-Practical** - Task 13-14 Lab Answers

## Key Learnings in Short

- Total Ports: 65535. Common: 80/HTTP, 443/HTTPS, 139/NETBIOS, 445/SMB
- `Nmap -sT` = Full Connect, logged, slow. `Nmap -sS` = SYN Half-Open, stealthy, fast, Industry Standard.
- If no response to FIN/NULL/Xmas -> Port is Open|Filtered
- If firewall blocks ICMP -> Use `-Pn`. Always use `-Pn` in TryHackMe.
- Search scripts with `grep -i <keyword> script.db`, not with `ls`.

## Quick Commands (Task 14)

```bash
nmap MACHINE_IP -sX -p 1-999 -Pn -vv
sudo nmap MACHINE_IP -sS -p 1-5000 -Pn
nmap -p 21 --script=ftp-anon MACHINE_IP -Pn
```
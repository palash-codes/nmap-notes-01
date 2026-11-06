# Task 13-14: Firewall Evasion & Practical Lab

## Task 13: Firewall Evasion

**Problem:** Target blocks ICMP (Ping). So normal scan fails.

**Q1. Check ICMP:**
```bash
ping MACHINE_IP
```
**Answer: N (No Response)**
Reason: Target blocks ICMP.

**Solution:** Use `-Pn` (No Ping) to scan without ping.

**Evasion Techniques to Bypass Firewall:**
```bash
nmap -Pn --source-port 53 -f --data-length 200 MACHINE_IP
```
- `-Pn` = Skip ping discovery
- `-f` = Fragment packets (break into small pieces so firewall cannot catch)
- `--data-length 200` = Change packet size to confuse firewall
- `--source-port 53` = Send from port 53 (DNS) - Firewall trusts DNS

## Task 14: Practical - 5 Questions with Answers

**Target: TryHackMe Lab Machine**

**Q1. Does target respond to ICMP (ping)?**
```bash
ping MACHINE_IP
```
Answer: **N**

**Q2. Xmas Scan on 1-999 ports, how many Open|Filtered?**
```bash
nmap MACHINE_IP -sX -p 1-999 -Pn -vv
```
Answer: **999**
Reason: No response received.

**Q3. What is the reason for 999 Open|Filtered?**
Answer: **No Response**

**Q4. SYN Scan on 1-5000 ports, how many Open?**
```bash
sudo nmap MACHINE_IP -sS -p 1-5000 -Pn
```
Answer: **5**

**Q5. Does FTP allow anonymous login?**
```bash
nmap -p 21 --script=ftp-anon MACHINE_IP -Pn
```
Answer: **Y (Yes)**
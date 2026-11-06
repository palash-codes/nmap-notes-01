# Task 10: NSE - Nmap Scripting Engine

## What is NSE?
- Nmap Scripting Engine
- Uses **Lua programming language**.
- Automates tasks like FTP anonymous login check, brute force, vulnerability scanning.

## Important NSE Commands
```bash
nmap -sC MACHINE_IP          # Run default scripts
nmap --script=vuln MACHINE_IP # Vulnerability scan
nmap --script=ftp-anon -p 21 MACHINE_IP # Check FTP anonymous
```

## NSE Script Categories (7+)
From notes (Page 7):
1. auth
2. broadcast
3. brute
4. default
5. discovery
6. dos
7. exploit
8. external
9. fuzzer
10. intrusive
11. malware
12. safe
13. version
14. vuln

> If we want to know how the server will be attacked, NSE scripts help us test for vulnerabilities before the real attack.
# Task 03-05: TCP NULL, FIN, Xmas Scans

These three scans belong to the same family and are used to bypass stateless firewalls.

### 1. TCP NULL Scan (-sN)
```bash
nmap -sN MACHINE_IP -Pn
```
- Sends packet with **no flags**.
- Behavior:
  - If port **closed** -> Target sends RST
  - If port **open** -> **No response**

### 2. TCP FIN Scan (-sF)
```bash
nmap -sF MACHINE_IP -Pn
```
- Sends packet with **FIN flag** only. FIN means Finish.
- Firewalls often block SYN packets but allow FIN packets to pass.
- Same behavior as NULL:
  - Closed = RST
  - Open = No response

### 3. TCP Xmas Scan (-sX)
```bash
nmap -sX MACHINE_IP -Pn
```
- Sends packet with **FIN, PSH, URG** flags set. The flags light up like a Christmas tree, hence the name Xmas.
- Closed = RST
- Open = No response

### Key Concept:
If you get **No Response**, Nmap marks it as **Open|Filtered** because it cannot be sure if the port is open or a firewall filtered the response.
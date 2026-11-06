# Task 11-12: Toolbox Concept & Searching Scripts

## Task 11: The Toolbox - 3 Parts of a Script

A Nmap Script has 3 parts:
1.  **Category = What is the work?** (e.g., Discovery, Vuln, Auth)
2.  **Script = What is the name?** (e.g., ftp-anon, smb-os-discovery)
3.  **Argument = How to run it?** (e.g., userdb, passdb)

Example Command Structure:
```bash
nmap --script=<category/script> --script-args=<arguments> MACHINE_IP
nmap --script=vuln --script-args=unsafe=1 MACHINE_IP
```

## Task 12: Searching Scripts - Correct Method

**Wrong Method (Folder Search):**
```bash
ls /usr/share/nmap/scripts/*smb*
# Only looks at folder names, slow.
```

**Correct Method (Database Search):**
```bash
grep -i smb /usr/share/nmap/scripts/script.db
grep -i ftp /usr/share/nmap/scripts/script.db
grep -i vuln /usr/share/nmap/scripts/script.db
```
- `script.db` is the real database containing all scripts.
- `ls` only sees the folder.
- For speed and accuracy, always search `script.db`.

**Interview Question:** What is the difference between `ls` and `script.db` for finding Nmap scripts?
Answer: `script.db` is the official database, faster and more accurate.
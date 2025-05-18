# 🔐 Ethical Hacking Project

## Scanning and Enumerating a Local Network with Nmap

## 🎯 Project Objectives

To understand and apply techniques in:

- Network scanning
- Service enumeration
- Vulnerability exploitation
- Privilege escalation
- Password cracking
- Security remediation

## 🛠 Tools Used

- Kali Linux (Attacker Machine)
- Metasploitable (Target Machine)
- Nmap
- John the Ripper
- Metasploit Framework

## 🔍 Task 1: Basic Network Scan

```
nmap -v 192.168.190.0/24
```

## 🧭 Task 2: Reconnaissance

### 2.1 Scanning for Hidden Ports
```
nmap -v 192.168.190.0/24
```

### 2.2 Service Version Detection
```
nmap -v -sV 192.168.129.0/24
```

### 2.3 Operating System Detection
```
nmap -v -O 192.168.190.0/24
```

## 📋 Task 3: Enumeration Summary

Open ports include services like vsftpd, OpenSSH, Ruby DRb RMI, mountd, java-rmi, nlockmgr, and status.

## ⚔️ Task 4: Exploitation of Services

- vsftpd 2.3.4: Exploited via known backdoor vulnerability.
- OpenSSH 4.7p1: Brute-force attack executed successfully.
- Java RMI: Remote code execution achieved via Metasploit module.

## 👤 Task 5: Creating a Privileged User

```
adduser isha
```
Password: hello

Hash in `/etc/shadow`:
```
isha:$1$fMBXympT$dR9NgYijwzq/mGMLikwd..
```

## 🔓 Task 6: Cracking Password Hash

Stored Hash in `isha.txt`:
```
isha:$1$fMBXympT$dR9NgYijwzq/mGMLikwd..
```

**Commands:**
```
john isha.txt
john isha.txt --show
```
Cracked Password: `hello`

## 🛡️ Task 7: Remediation and Recommendations

1. vsftpd 2.3.4 – vulnerable backdoor  
   **Fix**: Upgrade to vsftpd 3.0.5  
2. OpenSSH 4.7p1 – outdated, brute-forceable  
   **Fix**: Upgrade to OpenSSH 9.6  
3. Java RMI Service – allows remote execution  
   **Fix**: Disable or firewall restrict access

## 🎓 Major Learnings

- Applied Nmap for full-range scanning and OS detection.
- Understood enumeration and real-world exploitation techniques.
- Gained skills in privilege escalation and hash cracking.
- Learned how to evaluate vulnerabilities and apply proper remediation.

> 📘 This project simulates a real-world penetration test using open-source tools and is intended strictly for educational purposes.

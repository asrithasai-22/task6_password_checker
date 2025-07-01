# Password Strength Checker and Security Analysis

This project analyzes and compares password strength using **Kali Linux command-line tools** and the **PasswordChecker.com** web tool. It demonstrates how password complexity, randomness, and length impact security, and summarizes best practices against common attacks.

---

## Project Overview

| Category       | Tools / Platforms Used                         |
|----------------|------------------------------------------------|
| CLI-based      | Kali Linux (cracklib-check, grep, Python, etc.)|
| Web-based      | [PasswordChecker.com](https://passwordchecker.com) |
| Output         | HTML report + Python script + markdown analysis|

---

## Files Included


---

## Tools & Techniques Used

### Kali Linux CLI
- `cracklib-check` – Validates password strength against known patterns
- `grep` + `rockyou.txt` – Simulates dictionary attacks
- `python3` + `zxcvbn` – Measures entropy and structure of passwords
- `hashcat` *(optional)* – Demonstrates hash cracking potential

### Online GUI
- [PasswordChecker.com](https://passwordchecker.com) – Scored each password (0–4) with visual meter
- Provided real-time feedback like “Too short”, “Common password”, “Strong”, etc.

## Passwords Tested

| Password                         | Source     | Complexity | Cracklib | Zxcvbn Score | Dictionary Match |
|----------------------------------|------------|------------|----------|--------------|------------------|
| `Password123`                    | Manual     | Low        | Weak     | 1/4          | Yes              |
| `xK8#qP$2mL!9zR*5`               | Openssl    | High       | Strong   | 4/4          | No               |
| `ThisIsASuperLongSecurePassphrase2025` | Manual | Very High | Strong   | 4/4          | No               |


## How to Run This Project

### Kali Linux Method

Install required tools:

```bash
sudo apt update
sudo apt install cracklib-runtime pwgen python3-pip -y
pip install zxcvbn

# Check with cracklib
cat pass1.txt | cracklib-check

# Dictionary attack simulation using rockyou
grep -Fx "Password123" /usr/share/wordlists/rockyou.txt

# Python entropy and feedback analysis
python3 check_strength.py

**Date of Report**
February 20, 2024

This report was generated in a virtual environment using Kali Linux tools and PasswordChecker.com Website.

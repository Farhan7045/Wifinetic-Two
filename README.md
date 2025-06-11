## 🔓 Wifinetic Two | HackTheBox Walkthrough

> 🎯 Difficulty: Medium; 🖥️ OS: Linux; 📡 Type: Web + Wireless + Privilege Escalation

---

## 🧠 Overview

**Wifinetic Two** is a HackTheBox machine that combines web exploitation and wireless post-exploitation. This challenge involves:
- Exploiting a vulnerable **OpenPLC** web server using default credentials
- Achieving **remote code execution (RCE)** with an authenticated exploit
- Gaining initial shell access
- Leveraging a wireless interface to **brute-force a WPS-enabled network**
- Using Wi-Fi credentials to SSH into a router and capture the root flag

---

## 📑 Summary of the Attack Path

### 🔍 1. Enumeration
- Full port scan with `nmap`
- Found port `8080` running **OpenPLC v3**
- Port `22` open for SSH

### 🔓 2. Exploitation
- Default credentials `openplc:openplc` worked on `/login`
- Used a known Python exploit (Exploit-DB #49803) to achieve **RCE**
- Uploaded and modified exploit for reverse shell connection

### 🪜 3. Privilege Escalation
- Shell received as **root**
- Observed that `user.txt` flag was in `/root/` — unusual
- Found **`wlan0`** interface present

### 📶 4. Wireless Post-Exploitation
- Scanned Wi-Fi using `iw`
- Used **OneShot** tool to brute-force WPS and recover Wi-Fi credentials
- Connected to `plcrouter` via `wpa_supplicant`
- Assigned IP manually, then SSH’d into `192.168.1.1` as root

---

## 🏁 Flags

| Flag Type | Value |
|-----------|-------|
| 👤 User | `8fa8bdad612e447a18604faee1c84822` |
| 👑 Root | `480747d784dc6d2bf60abf04fac0df1d` |

---

## 📄 Walkthrough

A detailed PDF walkthrough is included in this repository:
- 📎 [**Wifinetic Two.pdf**](./Wifinetic%20Two.pdf)

The writeup covers each step in depth, including:
- Screenshots of the exploit and shell
- Modified Python script snippets
- Wi-Fi cracking configuration
- SSH connection to target

---

## 🙋‍♂️ Author

👨‍💻 **Farhan7045**  
🔗 GitHub: [github.com/Farhan7045](https://github.com/Farhan7045)

---

> 📝 This walkthrough is for educational purposes only. Always follow ethical hacking guidelines and practice on legal platforms like HackTheBox.

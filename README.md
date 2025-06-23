
# 🔍 Cyber Security Internship – Task 1

## 📌 Task: Scan Your Local Network for Open Ports

### 🎯 Objective:
Perform a basic port scan on your local network to identify open ports and understand network exposure.

---

## 🧰 Tools Used:
- ✅ Nmap v7.94 (Command-line tool)
- ❌ Wireshark (Optional, not used in this task)

---

## 🖥️ Target Network Info:
- **Target IP Range:** `192.168.56.0/24`
- **Scanned Host:** `192.168.56.1`

---

## 📄 Scan Command Used:
```bash
nmap -sS 192.168.56.0/24
```

---

## ✅ Scan Results:
Only one host was found active on the network:

### 🔹 192.168.56.1 — Open Ports:
| Port | Service       | Description |
|------|----------------|-------------|
| **135/tcp** | `msrpc`        | Microsoft RPC – used for Windows remote procedure calls |
| **139/tcp** | `netbios-ssn`  | NetBIOS Session Service – used for file/printer sharing in LAN |
| **445/tcp** | `microsoft-ds` | SMB over TCP – used for Windows file sharing |

---

## ⚠️ Risk Analysis:

- **Port 135 (MSRPC):**
  - Used internally for system communication.
  - If exposed, can be targeted by malware/worms.

- **Port 139 (NetBIOS-SSN):**
  - Used in LAN for file and printer sharing.
  - Can leak sensitive shared resources if not secured.

- **Port 445 (SMB):**
  - Common target of ransomware (like WannaCry).
  - Should be blocked from public access or hardened with strong authentication.

---

## 🛡️ Recommendations:

- Disable unused services like file/printer sharing.
- Use Windows Defender Firewall to block these ports on public networks.
- Never expose these ports to the internet.

---

## 🗂️ Files Included:
- `scan_result.txt`: Raw output of Nmap scan
- `README.md`: Explanation and analysis of the scan

---

## 📚 Concepts Learned:
- Port scanning using TCP SYN (`-sS`) method
- Understanding common ports and their risks
- Basic network reconnaissance

---

## 📤 Submission:
Uploaded to GitHub and submitted via the internship task form.

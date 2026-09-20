# 🔐 Week 3 – Password Cracking with John the Ripper (JTR)

![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper-red)
![Platform](https://img.shields.io/badge/Platform-Windows-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

---

## 📌 Executive Summary

This report documents the completion of **Week 3 – Project Module 1 (W3-PM1)** of the Networkwalks Cybersecurity & Ethical Hacking program. The task involved recovering the password of a protected PDF file (`My Locked PDF1.pdf`) using **John the Ripper (JTR)** and its graphical interface, **Johnny**, on a Windows PC.

The exercise demonstrated how password cracking tools work, the process of extracting hashes from protected files, and the practical difference between **encryption** and **hashing**. The password was successfully recovered and the protected PDF was opened, confirming successful completion of the module.

---

## 🎯 Objectives

1. Install John the Ripper and Johnny GUI on a Windows system
2. Extract the password hash from a protected PDF file
3. Save the hash in the correct `$pdf$...` format for JTR
4. Configure Johnny to use the John the Ripper executable
5. Execute a password cracking attack against the extracted hash
6. Recover the PDF password and open the protected file
7. Understand the difference between encryption and hashing

---

## 🧰 Tools Used

| Tool | Purpose |
|------|---------|
| **John the Ripper (JTR)** | Command-line password cracking tool |
| **Johnny** | Graphical (GUI) version of John the Ripper |
| **OnlineHashCrack PDF Hash Extractor** | Extracts the hash from the protected PDF |
| **Windows Notepad** | Saves the extracted hash to a `.txt` file |
| **Windows 11 PC** | Host operating system for the exercise |

> **Note:** John the Ripper comes pre-installed on Kali Linux. On Windows, it must be downloaded and installed separately.

---

## 📖 Background

John the Ripper (JTR) is a popular password cracking tool used by security professionals to test password strength. It originally targeted Unix systems but now supports Windows, Linux, and macOS. It can handle many types of password hashes and can also unlock password-protected files such as PDF, ZIP, and Office documents.

Johnny is the graphical version of John the Ripper. It provides a simple point-and-click interface, allowing beginners to use JTR without typing long commands.

In this lab, JTR and Johnny were used to recover the password of a protected PDF file, illustrating how password cracking works and why strong passwords are essential for protecting sensitive data.

---

## 🚀 Activities Performed

### 5.1 Download and Installation

**Step 1 — Download John the Ripper**

John the Ripper was downloaded from the official Openwall website:

🔗 https://www.openwall.com/john/

The Windows 64-bit Jumbo build was selected for installation.

**Step 2 — Download and Install Johnny GUI**

Johnny was downloaded from the official Openwall wiki:

🔗 https://openwall.info/wiki/john/johnny

The Windows binary `johnny_2.2_win.zip` was selected. The installer (`johnnyInstaller.exe`) was executed and installation completed successfully.

---

### 5.2 Hash Extraction

**Step 3 — Extract the PDF Hash**

The protected PDF file was uploaded to the OnlineHashCrack PDF Hash Extractor:

🔗 https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php

The tool generated a hash in the following format:


> **Important Note:** Any extra characters (e.g., `b'` at the start) were removed before saving, to ensure the hash was in the correct `$pdf$...` format.

**Step 4 — Save the Hash**

The hash value was pasted into Windows Notepad and saved as `hash1.txt`.

---

### 5.3 Configuration and Attack

**Step 5 — Configure Johnny**

Johnny was opened and the following configuration was applied:

1. Navigated to **Settings**
2. Clicked **Browse** next to "John the Ripper executable"
3. Selected the John the Ripper executable path

**Step 6 — Execute the Password Cracking Attack**

1. Clicked **Open password file** → selected `hash1.txt`
2. Clicked **Start new attack**
3. Waited for Johnny to recover the password

The password was successfully recovered and displayed in the **Password** column of the Johnny interface.

**Step 7 — Open the Protected PDF**

The protected PDF was opened and the recovered password was entered. The file opened successfully, confirming the password was correct.

---

## 📊 Results

| Item | Value |
|------|-------|
| Target File | `My Locked PDF1.pdf` |
| Hash Format | `$pdf$1*2*40*...` |
| Tool Used | Johnny (JTR GUI) |
| Password Recovered | ✅ Yes |
| PDF Opened Successfully | ✅ Yes |
| Attack Duration | Varies based on machine speed and password complexity |

---

## 🔑 Key Concepts Learned

### Encryption vs. Hashing

| | **Encryption** | **Hashing** |
|---|---|---|
| Type | Two-way function | One-way function |
| Reversible? | ✅ Yes (with key) | ❌ No |
| Purpose | Protect sensitive information | Validate integrity |
| Example | PDF password protection | Password storage |

**Key Takeaway:** Encryption is a two-way function — what is encrypted can be decrypted with the proper key. Hashing is a one-way function that scrambles plain text to produce a unique message digest. Passwords should always be stored as **hashes**, not encrypted. However, weak passwords can still be cracked — which is why strong passphrases and Multi-Factor Authentication (MFA) are essential.

---

## 🌍 Real-World Context

Password-related breaches continue to cause significant damage across Africa and globally:

| Year | Country | Incident |
|------|---------|----------|
| 2026 | South Africa | MTN Group breach — 5,700+ customers in Ghana affected |
| 2025 | Namibia | Telecom Namibia refused ransom; billing data leaked |
| 2025 | Senegal | National tax authority ransomware attack |
| 2024 | Uganda | Bank of Uganda hacked — **$16.8M stolen** |
| 2024 | Nigeria | Flutterwave hacked — **$7M diverted** |
| 2024 | South Africa | Cell C breach — **2TB leaked, 7.7M customers** |
| 2024 | Kenya | KURA data breach — government infrastructure exposed |
| 2024 | Cameroon | ENEO cyberattack — power management apps suspended |

These incidents highlight why **strong passwords, MFA, and proper hashing** are non-negotiable in modern cybersecurity.

---

## ⚠️ Risk Analysis / Impact

| # | Observation | Impact | Risk Level |
|---|-------------|--------|------------|
| 1 | Weak password on protected PDF | Password recovered quickly using JTR | Medium |
| 2 | Password reuse across systems | One cracked password may grant access to multiple accounts | High |
| 3 | Lack of MFA on protected files | Single factor of protection easily bypassed | High |
| 4 | Use of common dictionary words | Vulnerable to dictionary attacks | Medium |
| 5 | No password complexity policy | Increases likelihood of successful cracking | Medium |

**Risk level key:** Critical \| High \| Medium \| Low

> The risks above are observations from the password cracking exercise. The practical exercise involved recovering a lab-provided password and did not target any production systems.

---

## ✅ Recommendations

1. **Use strong, complex passphrases** — Combine upper and lower case letters, numbers, and symbols. Length matters more than complexity.
2. **Enable Multi-Factor Authentication (MFA)** — Even if a password is cracked, MFA provides an additional layer of protection.
3. **Avoid password reuse** — Use unique passwords for every account and file.
4. **Use a password manager** — Generate and store strong, unique passwords securely.
5. **Store passwords as hashes** — Never store passwords in plaintext or using reversible encryption.
6. **Use strong encryption for sensitive files** — Protect PDFs, ZIPs, and Office documents with strong, unique passwords.
7. **Conduct regular password audits** — Test password strength across systems using authorized tools.
8. **Educate users** — Train employees and individuals on password hygiene best practices.
9. **Perform security testing with authorization** — Password cracking should only be performed on systems and files you own or have explicit written permission to test.

---

## 🏁 Conclusion

During Week 3 of my Cybersecurity & Ethical Hacking internship at Networkwalks, I successfully completed the Password Cracking with John the Ripper module.

I installed John the Ripper and Johnny GUI on Windows, extracted a hash from a protected PDF file, saved it in the correct format, and used Johnny to recover the password. The PDF was then opened successfully with the recovered password.

This exercise reinforced the importance of strong passwords and helped me understand the fundamental difference between encryption (two-way) and hashing (one-way). It also demonstrated how quickly weak passwords can be cracked and why MFA and password managers are essential defenses.

I also learned that password cracking tools must only be used within an authorized scope, on systems and files you own or have explicit permission to test. This activity was completed as part of the assigned educational cybersecurity lab.

---

## ✅ Completion Status

- [x] John the Ripper installed
- [x] Johnny GUI installed
- [x] PDF hash extracted
- [x] Hash saved to `hash1.txt`
- [x] Password successfully cracked
- [x] PDF opened with recovered password
- [x] Documentation completed

---


---

## 🙏 Acknowledgements

Special thanks to my instructor **Waqas Karim** (CCIE) and **Networkwalks** for the hands-on guidance throughout this program.

---

## 👤 Author

**Oboth Richard**
Cybersecurity Professional — Batch B082

🔗 **LinkedIn:** [oboth-richard-5178933b8](https://lnkd.in/p/dKWzTGsb)

🔗 **GitHub Repository:** [Week 3 — Password Cracking with JTR](https://github.com/your-username/week3-password-cracking-jtr)

---

## ⚠️ Disclaimer

This project was completed in an **authorized educational lab environment** as part of the Networkwalks Cybersecurity & Ethical Hacking program.

- All activities were performed on **lab-provided files** and **systems I own or have permission to test**.
- This report is for **educational and research purposes only**.
- **Do not** use these techniques on systems you do not own or have explicit written permission to test.
- Unauthorized access is a **criminal offense** in most countries — even when nothing is damaged.

The instructor, authors, and Networkwalks are not responsible for any misuse of this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job, and a permanent record.

---

⭐ **If you found this useful, consider giving the repo a star!**


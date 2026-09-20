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

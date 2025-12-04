# Wi-Fi Security Assessment Lab (aircrack-ng)

This repository documents a personal Wi-Fi security assessment I performed on my own network to evaluate the strength of the wireless password and improve overall security.

> ⚠️ Disclaimer:  
> All tests were performed only on networks that I own or have explicit permission to test.  
> This project is for learning, auditing, and defensive security purposes only.

---

## 🎯 Objective

- Assess the strength of my personal Wi-Fi password.
- Practice a legal wireless security workflow using standard tools.
- Understand how attackers might target weak configurations.
- Apply hardening steps to improve Wi-Fi security.

---

## 🧪 Lab Environment

- **Operating System:** Kali Linux
- **Wireless Adapter:** External Wi-Fi adapter with monitor mode support
- **Tools Used:**
  - `aircrack-ng` suite (for capture & offline password testing)
  - Terminal / shell utilities
- **Target Network:** Personal Wi-Fi network (own/authorized)

No real SSIDs, BSSIDs, MAC addresses, or passwords are stored in this repo.

---

## 🔍 Methodology (High-Level)

This is a high-level summary of the steps followed during the assessment.

1. **Scope Definition**
   - Confirmed that only my own authorized Wi-Fi network will be tested.
   - Noted router model, expected encryption type (WPA2/WPA3), and password policy.

2. **Wireless Reconnaissance (Passive Scanning)**
   - Observed nearby access points and confirmed:
     - My Wi-Fi SSID
     - Channel and frequency
     - Encryption type (WPA2-PSK/WPA3 etc.)
   - Avoided storing or publishing any third-party network details.

3. **Handshake Capture (Own Network Only)**
   - Switched the wireless adapter to monitoring mode.
   - Captured the handshake of **only my network** for offline analysis.

4. **Password Strength Testing (Offline)**
   - Used `aircrack-ng` in offline mode against the captured handshake.
   - Tested the password using a wordlist to simulate a common attacker approach.
   - Verified at which complexity level the password becomes resistant.

5. **Validation & Hardening**
   - Verified that the key recovered matches the current Wi-Fi password.
   - Updated router configuration with:
     - Stronger, longer passphrase
     - Avoiding dictionary words
     - Optional: Separate guest network & unique password

---

## ✅ Findings (Example Template)

- **Wi-Fi Encryption:** WPA2-PSK
- **Initial Password Strength:** Weak / Medium / Strong (fill according to your test)
- **Crack Result:**
  - Was the password found? Yes / No
  - Approximate time to crack (if tested): Short / Moderate / High
- **Main Risk:**
  - Password susceptible to dictionary / weak wordlist attacks.
  - Device names / personal info used in password (if applicable).

*(Do not publish the actual password.)*

---

## 🛡️ Hardening Measures Applied

After the test, I:

- Changed the Wi-Fi password to:
  - 14+ characters
  - Mix of letters, numbers, and symbols
  - No reuse of personal names, birthdays, or common words
- Checked router settings:
  - Disabled WPS (if enabled).
  - Ensured WPA2 or WPA3 is enabled (not WEP/WPA).
  - Optionally enabled a separate guest network.

---

## 📂 Repository Contents

```text
wifi-security-assessment-aircrack-ng/
│── README.md
└── code/
     └── wifi_security_test_notes.txt

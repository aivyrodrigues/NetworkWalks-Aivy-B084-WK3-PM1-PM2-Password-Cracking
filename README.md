<div align="center">

# 🔓 Password Cracking Lab — JTR & Networkwalks Tools

**Recovering protected PDF passwords through hash extraction and dictionary attacks**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Week-03-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Tool-John%20the%20Ripper%20(JTR)-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/GUI-Johnny-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Target-My%20Locked%20PDF1.pdf-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Password%20Cracking-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Skill-Ethical%20Hacking-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Aivy%20Rodrigues-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This lab covers **Week 3** of the cybersecurity project series across two modules:

- **Project Module 1:** Password cracking on a protected PDF (`My Locked PDF1.pdf`) using **John the Ripper (JTR)** and its graphical frontend **Johnny**.
- **Project Module 2:** Password cracking on a protected PDF (`My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf`) using browser-based **Networkwalks Tools** (**Hash Calculator** and **Password Cracker**).

When a file is password-protected, its password is stored or derived in a hashed/encrypted structure. Extracting a crackable `$pdf$...` hash and testing candidate passwords against it demonstrates how dictionary attacks work and why weak or predictable passwords are vulnerable.

---

## 🎯 Objectives

- Understand password hashing vs. encryption and how protected files store credential verification data.
- Extract a crackable `$pdf$...` hash from `My Locked PDF1.pdf`.
- Configure **Johnny** with the **John the Ripper** (`john.exe`) executable on Windows (or use JTR pre-installed in Kali Linux).
- Run dictionary/password-cracking attacks using both **JTR / Johnny** and **Networkwalks Browser Tools**.
- Recover the PDF password, unlock the documents (`My Locked PDF1.pdf, My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf`), and capture the flags.

---

## 🛡️ Purpose & Ethical Use

This lab is designed to build practical awareness of password strength and attack mechanics in a controlled learning environment.

⚠️ **Important:** Only test files, hashes, and systems that you own or have explicit authorisation to assess. Never use password-cracking tools against unauthorised targets.

---

## ⚙️ Lab Environment & Tools

| 🧩 Component | ⚙️ Details |
| :--- | :--- |
| 🖥️ **Operating System** | Windows (or Kali Linux with JTR pre-installed / browser access) |
| 📄 **Target Files** | `My Locked PDF1.pdf, My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` |
| 🔨 **Module 1 Tools** | John the Ripper (Jumbo) & Johnny GUI (`johnny_2.2_win.zip` / `johnnyInstaller.exe`) |
| 🌐 **Module 2 Tools** | Networkwalks Hash Calculator & Networkwalks Password Cracker |
| 🔑 **Cracked Passwords** | `good_luck, password1` |
| 🚩 **Results** | Unlocked `My Locked PDF1.pdf, My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` and captured both flags |

---

# 🪜 Lab Procedure

## Module 1: Password Cracking with JTR & Johnny

### Step 1. Download John the Ripper & Johnny GUI
Download John the Ripper (Jumbo recommended for broader hash and format support) and Johnny GUI:
- **John the Ripper:** [https://www.openwall.com/john/](https://www.openwall.com/john/) or [https://distro.ibiblio.org/openwall/projects/john/1.9.0/](https://distro.ibiblio.org/openwall/projects/john/1.9.0/)
- **Johnny GUI:** [https://openwall.info/wiki/john/johnny](https://openwall.info/wiki/john/johnny)

*(Note: On Kali Linux, John the Ripper is available directly in the terminal without separate installation.)*

### Step 2. Install & Link `john.exe` in Johnny
1. Extract and run `johnnyInstaller.exe` to install **Johnny**.
2. Launch **Johnny**, open **Settings**, and click **Browse**.
3. Navigate to the `run` directory inside your extracted John the Ripper folder and select `john.exe` (e.g., `...\john-1.9.0-jumbo-1-win64\run\john.exe`).
4. Confirm that Johnny detects the John the Ripper executable.

### Step 3. Extract & Save the PDF Hash
1. Download `My Locked PDF1.pdf`.
2. Open the PDF hash extractor at [https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php) (which uses `pdf2john`).
3. Browse to `My Locked PDF1.pdf`, click **Upload**, and copy the resulting `$pdf$...` hash string.
4. Paste the hash into **Notepad** and save it as `hash1.txt` (UTF-8).

### Step 4. Run the Crack & Open the PDF
1. In **Johnny**, select **Open password file** > **Open password file (PASSWD format)** and open `hash1.txt`.
2. Click **Start new attack** and wait for cracking to finish (`100%` cracked).
3. Note the recovered password (`good_luck`).
4. Open the protected PDF (`My Locked PDF1.pdf`) in your PDF reader, enter `good_luck`, and view the unlocked flag page.

---

## Module 2: Password Cracking with Networkwalks Tools

### Step 1. Download the Locked PDF
Download `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` from the Networkwalks lab page.

### Step 2. Extract the Hash Using Networkwalks Hash Calculator
1. Open the **Hash Calculator** in your browse:
   - **URL:** [https://networkwalks.com/hash-calculator/](https://networkwalks.com/hash-calculator/)
2. Select/drop `My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` into the tool to parse it and extract the `$pdf$...` hash.
3. Click **Copy** to copy the entire hash starting with `$pdf$`.

### Step 3. Crack the Hash Using Networkwalks Password Cracker
1. Open the **Password Cracker** in your browser:
   - **URL:** [https://networkwalks.com/password-cracker/](https://networkwalks.com/password-cracker/)
2. Paste the `$pdf$...` hash into the **PDF HASH ($PDF$...)** input box.
3. Keep the built-in wordlist active (or upload a custom `.txt` wordlist) and click **START CRACKING**.
4. Wait for the attack to complete—the matching password (`password1`) is displayed once found.

### Step 4. Unlock the PDF & Capture the Flag
Open the protected PDF, enter `password1`, and confirm that the document opens to display the flag.

---

# 🔎 Lab Verification

| ✅ Step / Check | 🎯 Expected Result |
| :--- | :--- |
| 🔗 Johnny + `john.exe` linked | Johnny detects the valid John the Ripper executable in **Settings** |
| 🧾 Hashes extracted | Full `$pdf$...` hash strings obtained from `My Locked PDF1.pdf, My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` |
| 🔓 Passwords recovered | `good_luck, password1` matched in Johnny and/or Networkwalks Password Cracker |
| 🚩 Documents unlocked | `My Locked PDF1.pdf, My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf` opens and shows the captured flags |

---

# 🐞 Notes

- **Clean Hash Formatting:** When saving a hash from `pdf2john` / hash extractors into a `.txt` file for JTR/Johnny, make sure there are no extra leading characters like `b'`—the hash should begin directly with `$pdf$`.
- **Copy Complete Hash:** Always copy the entire `$pdf$...` string without truncating any characters.
- **Runtime Variance:** Cracking speed depends on password complexity, wordlist size, and hardware performance.

---

# 💡 What I Learned

### 1. Hashing vs. Encryption
Encryption is a two-way process that protects data so it can be decrypted with the proper key, whereas hashing is a one-way function that produces a message digest. Password-protected files rely on cryptographic structures/hashes that cracking tools test against candidate guesses.

### 2. CLI vs. GUI & Browser Workflows
Using **John the Ripper / Johnny** shows how dedicated local cracking tools work, while **Networkwalks Hash Calculator and Password Cracker** demonstrate how browser-based tools can extract `$pdf$` hashes and run dictionary attacks without local installation.

### 3. Password Strength Matters
Even a simple variation like `password1` can be found quickly through dictionary/wordlist testing. Using longer, unpredictable passwords with mixed character sets makes brute-force and dictionary cracking significantly harder.

---

# 🔗 Tools & Resources

- **John the Ripper:** [https://www.openwall.com/john/](https://www.openwall.com/john/)
- **Johnny GUI:** [https://openwall.info/wiki/john/johnny](https://openwall.info/wiki/john/johnny)
- **Online Hash Crack (PDF Hash Extractor):** [https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
- **Networkwalks Hash Calculator:** [https://networkwalks.com/hash-calculator/](https://networkwalks.com/hash-calculator/)
- **Networkwalks Password Cracker:** [https://networkwalks.com/password-cracker/](https://networkwalks.com/password-cracker/)

---

# 👤 Author

**Aivy Rodrigues**\
B084

LinkedIn: [https://www.linkedin.com/in/aivy-rodrigues](https://www.linkedin.com/in/aivy-rodrigues)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 03 | **Project:** Password Cracking with JTR & Networkwalks Tools | **Repository:** GitHub

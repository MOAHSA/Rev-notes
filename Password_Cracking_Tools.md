# Password Cracking Tools and Techniques

## Common Password Cracking Tools

### 1. John the Ripper
- **Description:** Popular open-source password cracker, supports many hash types.
- **Use cases:** Cracking password hashes (MD5, SHA variants, NTLM), cracking archive passwords (ZIP, RAR), cracking simple hashes with wordlists.
- **Website:** https://www.openwall.com/john/

### 2. Hashcat
- **Description:** High-performance password cracking tool with GPU acceleration.
- **Use cases:** Cracking a wide range of hash algorithms, including bcrypt, WPA/WPA2 wifi handshakes, NTLM, MD5, SHA1, etc.
- **Website:** https://hashcat.net/hashcat/

### 3. Hydra
- **Description:** Network login cracker, supports various protocols.
- **Use cases:** Brute forcing login credentials on protocols like FTP, SSH, HTTP(S), SMB, Telnet, and more.
- **Website:** https://github.com/vanhauser-thc/thc-hydra

### 4. Aircrack-ng
- **Description:** Suite of tools for auditing wireless networks.
- **Use cases:** Capturing and cracking WPA/WPA2 wifi handshakes.
- **Website:** https://www.aircrack-ng.org/

### 5. Ophcrack
- **Description:** Windows password cracker using rainbow tables.
- **Use cases:** Recovering Windows local user passwords.
- **Website:** http://ophcrack.sourceforge.net/

---

## Techniques

### Dictionary Attack
- Use a wordlist of common passwords and variants.
- Fast and effective against weak passwords.

### Brute Force Attack
- Try all possible character combinations.
- Time-consuming; mostly used on short passwords.

### Rainbow Tables
- Precomputed hash tables for reversing cryptographic hashes.
- Faster than brute force but requires storage space.

### Hybrid Attack
- Combines dictionary and brute force by appending or prepending characters.

---

## Additional Resources

- **RockYou.txt Wordlist:** Common password list used for dictionary attacks.  
  Download link: https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt

- **Cain & Abel:** Windows password recovery tool with multiple cracking methods.  
  Website: http://www.oxid.it/cain.html

---



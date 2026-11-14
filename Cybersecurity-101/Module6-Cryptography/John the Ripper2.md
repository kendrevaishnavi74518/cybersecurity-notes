### **What is Zip2John?**
**Zip2John:** A tool in John the Ripper that extracts password hashes from a password-protected ZIP file and converts them into a format that John can understand for cracking.

- **Syntax**
```
zip2john [zip file] > [output file]
```
- Ex: zip2john zipfile.zip > zip_hash.txt
   - `zipfile.zip` – ZIP file whose password hash needs to be extracted.
   - `>` – Redirects the output into a file.
   - `zip_hash.txt` – Stores the extracted hash.

### **Cracking the Password**
```
john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt
```
This uses the RockYou wordlist to try possible passwords against the extracted hash.

- **Rar2John:** A tool in John the Ripper that extracts password hashes from a password-protected RAR archive and converts them into a format that John can understand for cracking.
- **Syntax: rar2john [rar file] > [output file]

- Ex: /opt/john/rar2john rarfile.rar > rar_hash.txt
   - `rarfile.rar` – RAR file whose password hash needs to be extracted.
   - `>` – Redirects the output into a file.
   - `rar_hash.txt` – Stores the extracted hash.

### **Cracking the Password**
```
john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt
```

- **SSH2John:** A tool in John the Ripper that converts an SSH private key (`id_rsa`) into a hash format that John can understand to crack its passphrase.

- Syntax: ssh2john [id_rsa file] > [output file]

- Ex: /opt/john/ssh2john.py id_rsa > id_rsa_hash.txt
   - `ssh2john` – Converts the SSH private key into a crackable hash format.
   - `id_rsa` – SSH private key file.
   - `>` – Redirects the output into a file.
   - `id_rsa_hash.txt` – Stores the extracted hash.

### **Cracking the Password**
```
john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt
```

**Important:** The password being cracked here is the passphrase protecting the private key, not the SSH account password.
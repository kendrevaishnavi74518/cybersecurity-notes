#### Use of Hashing
Password storage and data integrity:
   - It is important to note that this does not apply to password managers, where you must retrieve your password in cleartext.

- Three insecure practices when it comes to passwords:
   - Storing passwords in plaintext
   - Storing passwords using a deprecated encryption
   - Storing passwords using an insecure hashing algorithm

- rockyou.txt:  This password list came from RockYou, a company that developed social media applications and widgets. They stored their passwords in plaintext, and the company had a data breach. The text file contains over 14 million passwords. 

- A Rainbow Table is a lookup table of hashes to plaintexts, so you can quickly find out what password a user had just from the hash. A rainbow table trades the time to crack a hash for hard disk space, but it takes time to create.

- Linux Passwords - On Linux, password hashes are stored in /etc/shadow, which is normally only readable by root. They used to be stored in /etc/passwd, which was readable by everyone.
     - The shadow file contains the password information. Each line contains nine fields, separated by colons (:). The first two fields are the login name and the encrypted password. More information about the other fields can be found by executing man 5 shadow on a Linux system.
     -  The encrypted password field contains the hashed passphrase with four components: prefix (algorithm id), options (parameters), salt, and hash. It is saved in the format `$prefix$options$salt$hash`. 
     - The prefix makes it easy to recognise Unix and Linux-style passwords; it specifies the hashing algorithm used to generate the hash.

| **Prefix** | **Algorithm** |
| :--- | :--- |
| `$y$` | yescrypt is a scalable hashing scheme and is the default and recommended choice in new systems. |
| `$gy$` | gost-yescrypt uses the GOST R 34.11-2012 hash function and the yescrypt hashing method. |
| `$7$` | scrypt is a password-based key derivation function. |
| `$2b$`, `$2y$`, `$2a$`, `$2x$` | bcrypt is a hash based on the Blowfish block cipher, originally developed for OpenBSD but supported on recent versions of FreeBSD, NetBSD, Solaris 10 and newer, and several Linux distributions. |
| `$6$` | sha512crypt is a hash based on SHA-2 with 512-bit output, originally developed for GNU libc and commonly used on older Linux systems. |
| `$md5` | SunMD5 is a hash based on the MD5 algorithm, originally developed for Solaris. |
| `$1$` | md5crypt is a hash based on the MD5 algorithm, originally developed for FreeBSD. |

- MS Windows passwords are hashed using NTLM, a variant of MD4. They’re visually identical to MD4 and MD5 hashes, so it’s very important to use context to determine the hash type.

- On MS Windows, password hashes are stored in the SAM (Security Accounts Manager). MS Windows tries to prevent normal users from dumping them, but tools like mimikatz exist to circumvent MS Windows security. Notably, the hashes found there are split into NT hashes and LM hashes.

#### Password Cracking
Cracking Passwords with GPUs: 
   - Modern GPUs (Graphics Processing Units) have thousands of cores. They are specialised in digital image processing and accelerating computer graphics. Although they can’t do the same sort of work that a CPU can, they are very good at some mathematical calculations involved in hash functions. 
   -  Some hashing algorithms, such as Bcrypt, are designed so that hashing on a GPU does not provide any speed improvement over using a CPU; this helps them resist cracking.

Cracking on VMs:
   -  VMs (Lab Machines) normally don’t have access to the host’s graphics card(s).
   -  Performance degradation occurs as you use the CPU from a virtualised OS, and when your purpose is to crack a hash, you need every extra CPU cycle.

#### Hashcat
Basic syntax: hashcat -m <hash_type> -a <attack_mode> hashfile wordlist, where:

  - -m <hash_type> specifies the hash-type in numeric format. For example, -m 1000 is for NTLM. 
  - -a <attack_mode> specifies the attack-mode. For example, -a 0 is for straight, i.e., trying one password from the wordlist after the other.
  - `hashfile` is the file containing the hash you want to crack.
  - `wordlist` is the security word list you want to use in your attack.

To display: hashcat -m 1400 hash2.txt --show. 
- Hashcat stores every cracked hash in its potfile, and --show prints hash:password straight from that file.

#### Integrity Checking

HMACs - HMAC (Keyed-Hash Message Authentication Code) is a type of message authentication code (MAC) that uses a cryptographic hash function in combination with a secret key to verify the authenticity and integrity of data.

Working: 
 - The secret key is padded to the block size of the hash function.
 - The padded key is XORed with a constant called the inner pad, or ipad. In RFC 2104, the ipad is the byte 0x36 repeated until it matches the block size.
 - The message is hashed using the hash function with the XORed key.
 - The result from Step 3 is then hashed again with the same hash function but using the padded key XORed with another constant.
 - The final output is the HMAC value, typically a fixed-size string.

 the HMAC function is calculated using the following expression:

HMAC(K,M) = H((K⊕opad)||H((K⊕ipad)||M))
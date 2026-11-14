### Basic Terms
- Hashing functions are designed as one-way functions. In other words, it is easy to calculate the hash value of a given input; however, it is a hard problem to find the original input given the hash value. 
- In computer science, P and NP are two classes of problems that help us understand the efficiency of algorithms:
   - P (Polynomial Time): Class P covers the problems whose solution can be found in polynomial time. 
   - NP (Non-deterministic Polynomial Time): Problems in the class NP are those for which a given solution can be checked quickly, even though finding the solution itself might be hard. In fact, we don’t know if there is a fast algorithm to find the solution in the first place.

-  If you have the hashed version of a password, for example, and you know the hashing algorithm, you can use that hashing algorithm to hash a large number of words, called a dictionary. 
- You can then compare these hashes to the one you’re trying to crack to see if they match. If they do, you know what word corresponds to that hash- you’ve cracked it!
- This process is called a dictionary attack, and John the Ripper, or John as it’s commonly shortened, is a tool for conducting fast brute force attacks on various hash types.

#### Basic Syntax
Syntax: john [options] [filepath]
   - john : Invokes the tool
   - [options] : Specifies options you want to use
   - [filepath] : File containing the hash, we are trying to crack.

##### Automatic Cracking
Syntax: john --wordlist=/usr/share/wordlists/rockyou.txt [filepath]
   - `--wordlist`: Specifie wordlist mode
> Ex: john --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt

#### Identifying Hashes
- Hash-identifier, a Python tool that is super easy to use and will tell you what different types of hashes the one you enter is likely to be, giving you more options if the first one fails.
- To use:
  - you can use wget or curl to download the Python file hash-id.py from its GitLab page. 
  - Then, launch it with python3 hash-id.py

#### Format Specific Cracking
Syntax: john --format=[format] --wordlist=[path to wordlist] [path to file]
   - `--format=`: This is the flag to tell John that you’re giving it a hash of a specific format and to use the following format to crack it
   - [format]: The format that the hash is in.
> Ex: john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt

Note: If you’re dealing with a standard hash type, e.g. md5 as in the example above, you have to prefix it with `raw-`.To check if you need to add the prefix or not, you can list all of John’s formats using john --list=formats 

#### NTHash/NTLM
- NThash is the hash format modern Windows operating system machines use to store user and service passwords. It’s also commonly referred to as NTLM, which references the previous version of Windows format for hashing passwords known as LM, thus NT/LM.

- In Windows, SAM (Security Account Manager) is used to store user account information, including usernames and hashed passwords.
-  You can acquire NTHash/NTLM hashes by dumping the SAM database on a Windows machine, using a tool like Mimikatz, or using the Active Directory database: NTDS.dit. 

#### Cracking Hashes from /etc/shadow
- The /etc/shadow file is the file on Linux machines where password hashes are stored. It also stores other information, such as the date of last password change and password expiration information. It is usually only accessible by root user.

 ##### Unshadow
 - **unshadow:** A tool in John the Ripper that combines `/etc/passwd` and `/etc/shadow` files into a single file so that John can understand and crack the password hashes.
 - Syntax: unshadow [path to passwd] [path to shadow]
   - unshadow: Invokes the unshadow tool
   - [path to passwd]: The file that contains the copy of the /etc/passwd file you’ve taken from the lab machine
   - [path to shadow]: The file that contains the copy of the /etc/shadow file you’ve taken from the lab machine

Ex: unshadow local_passwd local_shadow > unshadowed.txt

> Note on the files:  When using unshadow, you can either use the entire `/etc/passwd` and `/etc/shadow` files, assuming you have them available, or you can use the relevant line from each.

- ** Single Crack mode** : In this mode, John uses only the information provided in the username to try and work out possible passwords heuristically by slightly changing the letters and numbers contained within the username.
   - Syntax: john --single --format=[format] [path to file]
   - Ex: john --single --format=raw-sha256 hashes.txt

> Note: If you’re cracking hashes in single crack mode, you need to change the file format that you’re feeding John for it to understand what data to create a wordlist from. You do this by prepending the hash with the username that the hash belongs to. `(username:hash)`

- **Word Mangling**: The process of modifying words in a wordlist by adding numbers, symbols, or changing letters to create different password combinations that might match a user's password. In John the Ripper, word mangling helps generate possible password variations to improve cracking chances.

- **GECOS:** A field in the Linux `/etc/passwd` file that stores additional user information, such as the user's full name, phone number, and other personal details.

John the Ripper can use this information to generate possible passwords during word mangling.

#### **What are Custom Rules?**

**Custom Rules:** Custom rules in John the Ripper allow users to define their own password modification patterns to generate possible password combinations based on known password structures.

##### **Common Custom Rule Modifiers**

| Modifier | Meaning                                     |
| -------- | ------------------------------------------- |
| `Az`     | Appends characters to the end of a word.    |
| `A0`     | Adds characters to the beginning of a word. |
| `c`      | Capitalises the first letter of a word.     |

##### **Character Sets**

| Character Set | Meaning                           |
| ------------- | --------------------------------- |
| `[0-9]`       | Any number from 0 to 9.           |
| `[A-Z]`       | Uppercase letters.                |
| `[a-z]`       | Lowercase letters.                |
| `[A-z]`       | Uppercase and lowercase letters.  |
| `[!£$%@]`     | Any one of the specified symbols. |

- Custom rules are defined in the `john.conf` file.


**Example:**
```
[List.Rules:PoloPassword]
cAz"[0-9] [!£$%@]"
```
This rule:
- `c` – Capitalises the first letter.
- `Az` – Appends characters to the word.
- `[0-9]` – Adds a number.
- `[!£$%@]` – Adds a symbol.

**Example password:** `polopassword` → `Polopassword1!`

### **Using Custom Rules**
**Syntax:**
```
john --wordlist=[path to wordlist] --rule=PoloPassword [path to file]
```

**Important:** Custom rules help John generate password variations dynamically instead of relying only on existing words in a wordlist.

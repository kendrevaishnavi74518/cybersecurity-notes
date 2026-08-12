## Offensive Security
- It focuses on proactively testing systems by attempting to break in, with goal of identifying weaknesses before attackers exploit them.
- Hacking refers to penetration testing, an ethical,legal, & structured method for identifying weaknesses so they can be addressed.
- A hacker is someone who uses these skills positively to improve security.

## Core Terms
1. Red Teaming: A structured, authorized attack methodology that simulates a real attacker to test effectiveness of defenses & find vulnerabilities.
2. Penetration Test: A structured security assessment where authorized tester attempts to identify & exploit vulnerabilities to understand real-world risk.
3. Vulnerability: Weakness or flaw in a sysytem,configuration that an attacker could abuse.
4. Exploit: Technique or method used to take advantage of vulnerability to achieve specific outcome.
5. Scope: Boundaries of what is allowed to be tested during engagement. It defines which systems,apps & actions are permitted & what is off-limits.
6. Enumeration: Collecting details about system,users and services to find weak points.
7. Credentials: Login details such as usernames & passwords that unlock access.
8. Authentication: Step that checks if someone or something is the actual entity they claim to be.
9. Dictionary attack: Trying a predefined wordlist to guess a password or username.

- Ethical hacking(Penetration Testing), is practice of testing systems in controlled manner.
   - Purpose is to test strength of security controls & defenses, uncover gaps, and help teams improve overall security posture.

- **Gobuster**, this tool runs in terminal and automates the scanning for web pages.
    - Command: gobuster dir -u <URL> -w <WORDLIST>
       - gobuster → Runs Gobuster.
       - dir → Directory/file enumeration mode.
       - -u <URL> → Target website.
       - -w <WORDLIST> → Wordlist containing possible directory/file names.
<br>

## A Valuable Target

Attackers often target **valid credentials** because gaining access to an account can unlock private and powerful areas of an application.

- **Sensitive functionality:** Access to restricted features that modify data or perform important actions.
- **User data:** Access to private information such as names, emails, and account details.
- **Administrative features:** High-level features that allow users to manage accounts, settings, or the application.
- **Further attack opportunities:** Authenticated access may reveal additional vulnerabilities that allow attackers to gain more access.

- Hydra, a password-testing tool that automates login attempts against target application using wordlist.
    - Command: hydra -l <USERNAME> -P <PASSWORD_LIST> <TARGET> http-post-form "/<LOGIN_PATH>:<FORM_DATA>:F=<FAILURE_TEXT>" -V

    - -l <USERNAME> → Username to test.
    - -P <PASSWORD_LIST> → Password wordlist.
    - <TARGET> → Target host/IP.
    - http-post-form → HTTP POST login form.
    - /<LOGIN_PATH> → Login page path.
    - <FORM_DATA> → Form fields containing ^USER^ and ^PASS^.
    - F=<FAILURE_TEXT> → Text indicating a failed login.
    - -V → Shows each attempt.
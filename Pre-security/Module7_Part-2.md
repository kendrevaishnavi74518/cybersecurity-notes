## Offensive Security
- It focuses on proactively testing systems by attempting to break in, with goal of identifying weaknesses before attackers exploit them.
- Hacking refers to penetration testing, an ethical,legal, & structured method for identifying weaknesses so they can be addressed.
- A hacker is someone who uses these skills positively to improve security.

## Core Terms
1. Red Teaming: A structured, authorized attack methodology that simulates a real attacker to test effectiveness of defenses & find vulnerabilities.
2. Penetration Test: A structured security assessment where authorized tester attempts to identify & exploit vulnerabilities to understand real-world risk.
3. Vulnerability: Weakness or flaw in a sytem,configuration that an attacker could abuse.
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

## Becoming Defender
**Defensive Security** focuses on understanding what needs to be protected & implementing security measures to prevent,detect & mitigate impact of potential attacks.

1. Prevention: Putting security controls in place to stop attacks before they happen, such as firewalls,antivirus software & regular patching.
2. Detection: Monitoring systems & networks to identify suspicious or malicious activity through logs,alerts & security tools.
3. Mitigation: Taking action during an incident to limit damage, such as blocking traffic, isolating affected systems, or disabling compromised accounts.
4. Analysis: Investigating what happened, how it happened, and which systems were affected by reviewing logs and other evidence.
5. Response and Improvement: Recovering from the incident and improving defenses to reduce the risk of similar attacks in the future.

- Defenders protect their organization's devices, servers, applications, data, and networks. Before applying security controls, they must identify and understand the systems and how they connect.

## Key Defender Principles

- Threat anticipation: Review the systems to protect, imagine realistic paths an attacker may take to achieve their goal.
- Attack awareness: Studying common attack chains & frameworks is incredibly useful for defenders.
- Risk prioritization: Focuses on identifying the most critical systems to guide security efforts and focus.
- Continuous adaptation: Defense is not a one-time set up. Threats and attackers evolve, techniques change, and vulnerabilities emerge.

## Key Terminology

- Blue Team: A group of cyber security defenders tasked with protecting systems and responding to threats.
- Client Infrastructure: The networks, servers, devices, and applications belonging to an organization that need protection.
- Visibility: The ability to see and monitor activity across systems to spot potential issues.
- Threat: A potential danger, such as a hacker or malware, that could harm systems or data.
- Prevention: Stopping threats before they can cause harm by blocking, restricting, or reducing opportunities for attack.
- Detection: The process of identifying threats or suspicious activity in networks and systems.
- Mitigation: Actions taken to reduce or stop the impact of a threat once it's identified.
- Risk: The likelihood and potential impact of a threat successfully harming an organization.

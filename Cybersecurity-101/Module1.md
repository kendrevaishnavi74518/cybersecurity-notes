## Search Skills
1. Shodan - 
It is often described as a search engine for IoT. It continuously scans the internet, searching for networking equipment,industrial control systems, traffic cameras, and virtually anything else with a public network connection to see what's running and where.

- Filters used to narrow down results:
    - country - Restricts to a specific country code.
    - port - Filter by specific port number or range.
    - org - Organization or ASN Identifier
    - hostname - Match against a specific hostname or domain.

2. VirusTotal - 
It collates results from over 70 antivirus engines & website scanners into single interface. Submit a file,URL,domain or file hash, it tells whether any of those engines have flagged it malicious or not.

3. Vulnerability Databases(CVE) - 
**Common Vulnerability and Exposure(CVE)** program is the closet to a universal dictionary of known vulnerabilities. Each confirmed vulnerability is assigned a unique identifier, format **CVE-YEAR-NUMBER**.
- If it is impactful enough, it may even get a moniker.
- These vulnerabilities are given a score(CVSS) based on
     - Impact: What damage it can lead to?
     - Complexity: Easy to exploit or not?
     - Availability: How likely someone can exploit?

4. Technical Documentation(MAN)
Official documentation should be your first source when learning or troubleshooting security tools.Linux man pages provide built-in documentation for many commands and cybersecurity tools.
- To view manual page, run man <command/tool>, eg. man nc(nc = netcat)

5. GitHub
It is a great resource for staying updated on latest threats & vulnerabilities. Researchers often publish proof-of-concept (PoC) code, exploitation tools, and detailed technical reports there, which are usually faster than official channels. 
- Not all PoCs are equally reliable. Some are incomplete, some are intentionally flawed, and occasionally a "PoC" repository is malicious itself. Always verify what you're about to execute.

  
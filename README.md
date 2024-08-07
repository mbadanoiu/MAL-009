# MAL-009: Insecure Chaining of Flags T and TT in Zip for Linux

In Zip for Linux, the “-TT” flag can be used to run arbitrary system commands. Due to the dangerous nature of this flag, it must always be used at the same time as the “-T” flag. By using a flag chaining attack, attackers that should only be able to insert just one flag in a zip command can insert both the “-T” and “-TT” flags and potentially execute malicious code.

### Proof Of Concept:

More details and the exploitation process can be found in this [PDF](https://github.com/mbadanoiu/MAL-009/blob/main/Zip%20-%20MAL-009.pdf).

Example of potentially vulnerable application can be found in this [python code](https://github.com/mbadanoiu/MAL-009/blob/main/exploit_me.py).

### Additional Resources:

This case study came to mind after exploiting [CVE-2020-8248: Privilege Escalation via Zip Wildcard Exploit in Pulse Secure VPN Linux Client](https://github.com/mbadanoiu/CVE-2020-8248/blob/main/Pulse%20Secure%20VPN%20Linux%20Client%20-%20CVE-2020-8248.pdf) as I was curious if the command execution via Zip could be achived with just 1 file instead of 2.

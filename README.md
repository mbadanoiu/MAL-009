# MAL-009: Insecure Chaining of Flags T and TT in Zip for Linux

In Zip for Linux, the “-TT” flag can be used to run arbitrary system commands. Due to the dangerous nature of this flag, it must always be used at the same time as the “-T” flag. By using a flag chaining attack, attackers that should only be able to insert just one flag in a zip command can insert both the “-T” and “-TT” flags and potentially execute malicious code.

### Proof Of Concept:

More details and the exploitation process can be found in this [PDF](https://github.com/mbadanoiu/MAL-009/blob/main/Zip%20-%20MAL-009.pdf).

Example of potentially vulnerable application can be found in this [python code](https://github.com/mbadanoiu/MAL-009/blob/main/exploit_me.py).

### Additional Resources:

This case study came to mind after exploiting [CVE-2020-8248: Privilege Escalation via Zip Wildcard Exploit in Pulse Secure VPN Linux Client](https://github.com/mbadanoiu/CVE-2020-8248/blob/main/Pulse%20Secure%20VPN%20Linux%20Client%20-%20CVE-2020-8248.pdf) as I was curious if the command execution via Zip could be achived with just 1 file instead of 2.

[Bug ticket](https://bugs.launchpad.net/ubuntu/+source/zip/+bug/1916081) concerning this vulnerability opened on bugs.launchpad.net on 18-Feb-2021

Other examples of Zip for Linux Flag Chaining leading to RCE:
- https://sonarsource.github.io/argument-injection-vectors/binaries/zip/
- [Multiple vulnerabilities in Dell Unisphere for PowerMax vApp, VASA Provider vApp and Solutions Enabler vApp CVE-2022-45103 / CVE-2022-45104](https://www.synacktiv.com/sites/default/files/2023-02/Synacktiv-Security_Advisory-Dell_EMC_vApp_Manager-Multiple_Vulnerabilities.pdf)
- [elFinder - A Case Study of Web File Manager Vulnerabilities](https://www.sonarsource.com/blog/elfinder-case-study-of-web-file-manager-vulnerabilities/)

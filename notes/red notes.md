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

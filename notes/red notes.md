#### 1. 启用 RDP 服务
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server" -Name "fDenyTSConnections" -Value 0

----

#### 2. 放行防火墙中的 RDP 端口（3389）
Enable-NetFirewallRule -DisplayGroup "Remote Desktop"

----


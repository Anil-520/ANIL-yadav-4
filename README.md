# ANIL-yadav-4
Basic firewall management skills and understanding of network traffic filtering.

LINUX (UFW)

# 1. Open terminal (no command needed, just start terminal)

# 2. List current firewall rules
sudo ufw status numbered

# 3. Block inbound traffic on port 23 (Telnet)
sudo ufw deny 23

# 4. Test the rule (try to connect)
telnet localhost 23   # or use nc -zv localhost 23

# 5. Allow SSH (port 22)
sudo ufw allow 22

# 6. Remove the Telnet block rule
sudo ufw delete deny 23

# 7. All commands above are the documentation
# 8. UFW filters traffic by allowing/denying packets based on rules

WINDOWS (powershe)

# 1. Open Windows PowerShell as Administrator

# 2. List current firewall rules
Get-NetFirewallRule

# 3. Block inbound traffic on port 23 (Telnet)
New-NetFirewallRule -DisplayName "Block Telnet" -Direction Inbound -LocalPort 23 -Protocol TCP -Action Block

# 4. Test the rule (try to connect)
Test-NetConnection -ComputerName localhost -Port 23

# 5. Allow SSH (port 22)
New-NetFirewallRule -DisplayName "Allow SSH" -Direction Inbound -LocalPort 22 -Protocol TCP -Action Allow

# 6. Remove the Telnet block rule
Remove-NetFirewallRule -DisplayName "Block Telnet"

# 7. All commands above are the documentation
# 8. Firewall filters traffic by applying allow/block rules to ports and protocols

!!!To run the script you have to make a .txt file in the same folder as the script with any IP you want to Block or Allow!!!
!!!Also you need to run the script as an administrator!!!

To run the script for IPv4 CIDR AllowList:
.\Import-Firewall-Blocklist-Allowlist.ps1 -RuleName "IPV4Allow" -action "allow" -protocol "TCP" -localport "80,443"

To run the script for IPv4 CIDR BlockList:
.\Import-Firewall-Blocklist-Allowlist.ps1 -RuleName "IPV4Block" -action "block" -protocol "TCP" -localport "80,443"

I tested the script using a .txt file that had many IPs in different lines.
Also I tested the script using a .txt file that had IPv6 IPs, the code for IPv6 Allow-Block List is:

.\Import-Firewall-Blocklist-Allowlist.ps1 -InputFile ".\IPV6.txt" -RuleName "IPV6Allow" -action "allow" -protocol "TCP" -localport "80-443"

.\Import-Firewall-Blocklist-Allowlist.ps1 -InputFile ".\IPV6.txt" -RuleName "IPV6Block" -action "block" -protocol "TCP" -localport "80-443"

You can run the script with any protocol that you want to Block or Allow. For example:

DNS:
.\Import-Firewall-Blocklist-Allowlist.ps1 -InputFile ".\IPV6.txt" -RuleName "IPV6Allow" -action "allow" -protocol "DNS" -localport "53"
.\Import-Firewall-Blocklist-Allowlist.ps1 -InputFile ".\IPV4.txt" -RuleName "IPV6Allow" -action "allow" -protocol "DNS" -localport "53"
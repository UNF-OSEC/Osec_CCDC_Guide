# Firewalls

ports, ips, domains, etc

### Starting The Firewall <a href="#starting-the-firewall" id="starting-the-firewall"></a>

* Get the status of the firewall: `C:\> Get-NetFirewallProfile | Format-Table Name, Enabled`
* Enable Firewall in Windows Server: `C:\> Set-NetFirewallProfile -Profile Domain, Public, Private -Enabled True`

***

### Firewall Rules <a href="#firewall-rules" id="firewall-rules"></a>

* Blocking Ports: `New-NetFirewallRule -DisplayName <name displayed> -Direction <Inbound/Outbound> -LocalPort <Port#> -Protocol <protocol name abbriev> -Action <Block/Allow>`
* Blocking IP/Domain: `New-NetFirewallRule -DisplayName "Blocked port 1234 for a specific IP address" -Direction Inbound -Protocol TCP -LocalPort 12345 -Action Block -RemoteAddress 192.168.3.152`

***

### GUI Firewall <a href="#gui-firewall" id="gui-firewall"></a>

most windows systems with a GUI desktop also have access to a gui version of Windows Defender Firewall that is much easier to use on your own.

To access this version go to your systems control pannel (found by searching for it on the start menue) then selecting System and Security, then Windows Defender Firewall.

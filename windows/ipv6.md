# IPv6

IPv6 is the new version of the IP protocol that is intended to solve the problems associated with the IPv4 version of the protocol.\
While in many cases it is useful to have avaliable for the case of competitions such as CCDC it is often un-nescessary and only serves to add an aditional vector of attack.

### Disabling and Enabling IPv6 <a href="#disabling-and-enabling-ipv6" id="disabling-and-enabling-ipv6"></a>

1. Get the name of the adapter you wish to modify `Get-NetAdapterBinding -ComponentID ms_tcpip6`

To Enable IPv6\
`Enable-NetAdapterBinding -Name "<AdapterName>" -ComponentID ms_tcpip6`

To Dissable IPv6\
`Disable-NetAdapterBinding -Name "<Adapter Name>" -ComponentID ms_tcpip6`

**To do so for all adapters**\
for adapter name use `*` instead of the name of a spescific adapter. E.X:\
`Enable-NetAdapterBinding -Name "*" -ComponentID ms_tcpip6`

***

_NOTE_ IPv6 Adapter likely named Teredo\
`netsh interface teredo show status`\
`netsh interface teredo set state disabled`

# Server Message Block (SMB)

Server Message Block (SMB) is a network file sharing protocol used by Microsoft Systems.

Over the years many SMB has proven to be a popular method of attacking systems and moving through networks.

***

### Detecting SMB <a href="#detecting-smb" id="detecting-smb"></a>

* SMB v1 `Get-WindowsOptionalFeature -Online -FeatureName SMB1Protocol`
* SMB v2/v3 `Get-SmbServerConfiguration | Select EnableSMB2Protocol`

### Disabling SMB <a href="#disabling-smb" id="disabling-smb"></a>

SMB is a default tool on many Windows Systems. This means that while it may be on a system or even running there is a good chance it is not entirely nescessary. If that is the case SMB should be dissabled.

* SMB v1 `Set-SmbServerConfiguration -EnableSMB1Protocol $false`
* SMB v2/v3 `Set-SmbServerConfiguration -EnableSMB2Protocol $false`

### Re-Enabling SMB <a href="#re-enabling-smb" id="re-enabling-smb"></a>

If you made a mistake and found that SMB is infact nescessary on the system here is how to re-enable it.

* SMB v1 `Set-SmbServerConfiguration -EnableSMB1Protocol $true`
* SMB v2/v3 `Set-SmbServerConfiguration -EnableSMB2Protocol $true`

### SMB v1 <a href="#smb-v1" id="smb-v1"></a>

If SMB v1 is running on a system it should be dissabled. This is because this version of SMB is vulnerable to the leaked NSA Eternal Blue exploit that is extremely easy for an attacker to use. This version of the service is outdated and extremely vulnerable.

### Other SMB Hardening <a href="#other-smb-hardening" id="other-smb-hardening"></a>

On public facing devices that do not require it you can block smb traffic by blocking TCP Port 445 and 139 , as well as UDP Ports 137-138.

***

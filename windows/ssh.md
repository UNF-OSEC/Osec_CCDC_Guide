# SSH

SSH is not a default tool on windows, despite this it is not uncommon for openSSH to be found installed on systems (especially those used in competition).

To start and stop the SSH service on Windows use `Start-service sshd` and `Stop-service sshd`

\*note: you may want to start ssh service start type to automatic `Set-Service -Name sshd -StartupType 'Automatic'`.

***

### SSH Config <a href="#ssh-config" id="ssh-config"></a>

The config file for OpenSSH on Windows can be found at the following path: `C:\Program Files\OpenSSH-Win64\sshd_config_default`

The following are items that can be appended to the end of the file you can use to help configure the access and privlidges of SSH.

* Allow connections onlyto a spescific domain security group: `AllowGroups <Domain>\<Group>`
* Allow access to a local user group `AllowGroups <groupName>`
* Deny access to a group: `DenyGroups Administrators`
* Require Public Key or Password (pick one): `PubkeyAuthentication yes`\
  `PasswordAuthentication yes`

After making changes run the command `restart-service sshd` for them to take effect.

# PAM

Pam path: `/etc/pam.d`

### Password Quality Rules <a href="#password-quality-rules" id="password-quality-rules"></a>

in the `/etc/security` directory file `pwquality.conf` can be edited to alter the rules for password quality.

* `difok` indicates number of chars from new passwd that must not be present in the old one
* `minlen` sets minimum passwd lenght
* `ucredit` sets number of uppercase chars required
* `lcredit` sets number of required lowercase chars
* `dictcheck` checks if passwd is in cracklib dictionary, enabled if set to not 0
* `usercheck` makes sure password does not contain username, enabled if set to not 0\
  USAGE: `minlen=7`

### sshd <a href="#sshd" id="sshd"></a>

Path: `/etc/pam.d/sshd`

* `auth requisite pam_nologin.so` checks if `/etc/nologin` exsists, if it does only root can log in to it.
* `auth include <option>` include default configuration for the following options: `common-auth,common-account, common-password, common-session` each requires its own line.
* `session required pam_loginuid.so` Sets the login UID process attribute for the process that was authenticated.

### For more information on PAM <a href="#for-more-information-on-pam" id="for-more-information-on-pam"></a>

* [https://documentation.suse.com/zh-cn/sles/12-SP5/html/SLES-all/cha-pam.html](https://documentation.suse.com/zh-cn/sles/12-SP5/html/SLES-all/cha-pam.html)
* [https://linuxhint.com/linux\_pam\_tutorial/](https://linuxhint.com/linux\_pam\_tutorial/)

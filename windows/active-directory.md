# Active Directory

Active Directory stores information about objects on a network to help Administrators. For attackers Active Directory is great for moving laterally through a network. The following section will cover the basics of securing Active Directory.

***

### Limit the use of Domain Admins and other Privileged Groups <a href="#limit-the-use-of-domain-admins-and-other-privileged-groups" id="limit-the-use-of-domain-admins-and-other-privileged-groups"></a>

Domain Admins have Admin access to every system on the domain. Recomended best practice is to only have the Default domain admin account, and temporarily give users Domain Admin Group as they need it, then remove it soon after.

The same is recommended for the Enterprise admin, Backup admin, and Schema admin groups.

To modify groups open the domain admin management console, right click on where user accounts are, from here you use the delegate control wizzard and select the option "Create, delete, and manage user accounts".

***

### Secure the Domain Admin account <a href="#secure-the-domain-admin-account" id="secure-the-domain-admin-account"></a>

The default Domain Admin account should only be used in limited circumstances. Ideally this account has an extremely long password that is kept in a secure location.

For more detailed recomendations on securing the Domain Admin account on AD see the following page:\
[https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/appendix-d--securing-built-in-administrator-accounts-in-active-directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/appendix-d--securing-built-in-administrator-accounts-in-active-directory)

***

### Local Admin <a href="#local-admin" id="local-admin"></a>

Whoever does not need to be in local admin should be removed from the group.

To do this using powershell first enter `Get-LocalGroupMember administrators` to show who is in the group.

To now remove members use\
`$members = "<userName>", "<Domain>\<email@outlook.com>" Remove-LocalGroupMember -Group "Administrators" -Member $members`

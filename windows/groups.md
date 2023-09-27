# Groups

### Changing Passwords <a href="#changing-passwords" id="changing-passwords"></a>

1. Open Windows Server Essentials dashbord
2. On the Navigate bar click User
3. Select the user whose Password you want to change
4. In the task panel for that user select Change Password
5. Enter and Confirm the New Password
6. Click Change

### Changing Password Policy <a href="#changing-password-policy" id="changing-password-policy"></a>

In the Windows Server Essentials dashboard select password policy then pick which options you wish to change.

passwords can also be changed in powershell using:\
`Set-ADAccountPassword -Identity $<user> -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "$<newPass>" -Force)`

Using CMD.exe you can do\
`net user /<domain> <USERNAME> <NEWPASS>`\
with the domain being optional for changing a user on a spescific domain.

***

Most User Opperations can be easily done in the Windows Server Essentials Pannel.

Here users can be added, removed, altered, deactivated, activated, and have permissions changed.

The same applies for groups which function in a similar manor.

Because this is a gui tool and relatively strait foreward im excluding spescific instructions

***

### User Management - Powershell <a href="#user-management-powershell" id="user-management-powershell"></a>

* List all User: `Get-WmiObject -ComputerName workstation1 -Class Win32_UserAccount -Filter" LocalAccount=True" | Select PSComputername, Name, Status, Disabled, AccountType, Lockout, PasswordRequired, PasswordChangeable | Out-GridView`
* Get Name, Status, and Description of account: `Get-LocalUser -Name <name>`
* get name of accounts: `net users`
* get list of remote sessions (gives session ID): `qwista` , you can use `qwinsta /server:SERVERIP` to spescify sessions on a spescific server.
* dissconnect remote sessions: `rwinsta /server:SERVERIP SESSIONID`
* Dissable User: `Disable-LocalUser` or `Disable-ADAccount`.
* Remove User: `Remove-LocalUser -Name “<username>”`
* Create a new user (Prompts the user for a password through Read-Host cmdlet → stores it as a\
  secure string in the $Password variable): `PS C:\> $Password = Read-Host -AsSecureString`
* Create a new user (Creates local user account by using password stored in $Password): `PS C:\> New-LocalUser "User" -Password $Password -FullName "Third User" -Description "Description of this account."`

# Powershell

Powershell is a scripting language for windows that is somewhat similar to Bash for linux. It uses a "pipeline" structure and Commandlets that function as individual commands within the language.

Many bash commands work in powershell including cat, cd, echo, pwd, and man.

### Common Commandlets <a href="#common-commandlets" id="common-commandlets"></a>

* `Get-Command` - list all powershell commands avaliable (adding a \* after gets all types of commands even non powershell) you can also add filters such as `Get-Command -Name *process*` to only show those with process in the name.
* `Get-Help <cmd>` - tells you how to use a spescific command
* `cls` - clear screen
* `set-location` - can be used as a alternative to cd to navigate the file system or by appending `-Path <C:\Path\To\Goto>` to go to a spescific path.
* `Get-ChildItem` - show content in current folder (alias is **dir**)
* `rm` or `rmdir` - delete files or folders
* `Get-Service` - list services installed on system
* `Get-Process` - list all running processes on system
* `Set-ExecutionPolicy` - allows you to set an execution policy, ex: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine`. Policies are Restricted, Unrestricted, Remote Signed, All Signed. use -List to list the policy.
* `Start-Service` and `Start-Process` - start a process or service. by `-Name <name>`
* `Stop-Service` and `Stop-Process` - stop process either by `-Name <name>` or `-ID <id>`
* `| Out-File C:Path\To\File` append this after a powershell command with a spescified path to save the output of that command to the spescified location

### Constrained Mode <a href="#constrained-mode" id="constrained-mode"></a>

Powershell has the option to be run in constrained mode, this is meant to limit the capabilities of Powershell to attampt to limit the ability of attackers.

* get current powershell language mode: `$ExecutionContext.SessionState.LanguageMode`
* set powershell language mode: `$ExecutionContext.SessionState.LanguageMode = "<languageModes>`

Avaliable language modes include the following:

* FullLanguage.
* RestrictedLanguage.
* ConstrainedLanguage (introduced in PowerShell 3.0)
* NoLanguage.

***

### Oneliner Port Scanner <a href="#oneliner-port-scanner" id="oneliner-port-scanner"></a>

`0..65535 | Foreach-Object { Test-NetConnection -Port $_ scanme.nmap.org -WA SilentlyContinue | Format-Table -Property ComputerName,RemoteAddress,RemotePort,TcpTestSucceeded }`

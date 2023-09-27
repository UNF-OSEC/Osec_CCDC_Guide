# Services

* View Running processes (Provides image (process) name, PID, Session Name, Session Number, and\
  Memory Usage): `tasklist | more`
* get more details on a spescific process: `get-process -ID <PID> | select-object *`
* get active connections, processes, source address and port, foriegn address and the state of the process: `Netstat -ab`
* Give PID for processes on active connections `Netstat -aon`

### Killing Processes <a href="#killing-processes" id="killing-processes"></a>

* force kill process via PID: `taskkill /PID <PID> /F`
* force kill process by name: `taskkill /IM [process-name] /F`
* Stop process by PID: `Stop-Process -ID <PID> -Force`
* Stop process by name: `Stop-Process -Name <ProcessName> -Force`

***

### Services <a href="#services" id="services"></a>

Windows servcies are applications that run in the background of your system that you generally do not interact directly with. Some services can be activated automatically at startup or have elevated privliges on the system.

Critical Services Includes but is not Limited To:\
● smss.exe\
● csrss.exe\
● wininit.exe\
● logonui.exe\
● lsass.exe\
● services.exe\
● winlogon.exe\
● System\
● svchost.exe with RPCSS\
● svchost.exe with Dcom/PnP

### Dissable Services <a href="#dissable-services" id="dissable-services"></a>

This requires running powershell as an administrator.

* List Services: `Get-Service`
* Stop a Service: `Stop-Service -Name "<SERVICE-NAME>"`
* Start a Service: `Start-Service -Name "<SERVICE-NAME>"`

### Misc Services to Dissable <a href="#misc-services-to-dissable" id="misc-services-to-dissable"></a>

It may be benificial to dissable some of these services if possiable.

* Winodows mobile hotspot services
* Print Spooler
  * Stop-Service -Name Spooler -Force
  * Set-Service -Name Spooler -StartupType Disabled
* Fax Service
* Maps Manager
  * `Get-Service -Name MapsBroker | Set-Service -StartupType Disabled`
  * `Stop-Service MapsBroker`
* Windows Biometric Service
* Broadcast DVR Server
* Windows 10 OneSyncSvc

***

### Tasks <a href="#tasks" id="tasks"></a>

* view schedueled tasks: `schtasks`
* get status of a task: `Get-ScheduledTask -TaskName “<taskName>”`
* kill target schedueled task: `Unregister-ScheduledTask -TaskName “<taskName>” -Confirm:$false`
* kill target task by taskname (cmd): `schtasks /Delete /TN “<task name>” /F`

***

### Other <a href="#other" id="other"></a>

The following link contains a list of Applications on Windows systems capable of bypassing Windows Defender, the antivirus built into Windows Systems. It also provides a list of rules for Windows Defender to block these applications.\
[https://learn.microsoft.com/en-us/windows/security/application-security/application-control/windows-defender-application-control/design/applications-that-can-bypass-wdac](https://learn.microsoft.com/en-us/windows/security/application-security/application-control/windows-defender-application-control/design/applications-that-can-bypass-wdac)

This link contains resources on how to add that policy.\
[https://desktop.gov.au/blueprint/abac/wdac-policy-creation.html](https://desktop.gov.au/blueprint/abac/wdac-policy-creation.html)

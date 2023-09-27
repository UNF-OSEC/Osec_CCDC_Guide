# Sysmon

[https://download.sysinternals.com/files/Sysmon.zip](https://download.sysinternals.com/files/Sysmon.zip)

Sysmon is a tool from the Windows sysinternals suite that is used to monitor and view system event logs. process creation, file changes, network connections, and loading of DLLs + Drivers.

After downloading sysmon using the command\
`Invoke-WebRequest -Uri https://raw.githubusercontent.com/olafhartong/sysmon-modular/master/sysmonconfig.xml -OutFile C:\Windows\config.xml` in Powershell install it using `sysmon64.exe –accepteula –i c:\windows\config.xml` (exclude the 64 for 32 bit systems).

On a system Sysmon Events can be viewed locally under `Applications and Services Logs > Microsoft > Windows > Sysmon` in the event viewer.

To access event viewer use the following selections `Start menu > Control Panel > Administrative Tools > Event Viewer`.

# Logging

windows has many logging tools to allow you to see what has been happening on your system. These are helpful for finding malicious activity on a system as well as monitoring the activity of legitimate users.

### Windows Event Viewer <a href="#windows-event-viewer" id="windows-event-viewer"></a>

The easiest way to access the Windows Event Viewer is through the control pannel. From there navigate to Administrative Tools then select Event Viewer. Alternatively it can be accessed through Server Manager by selecting Tools then Event Viewer.

This tool shows information about signifigant events on the system and provides a relatively easy way to sift through this information.

### Audits <a href="#audits" id="audits"></a>

Windows Audit Policy lets you choose what is logged on your system/server.

To access the basic audit policy configuration go to `Computer Configuration -> Windows Settings -> Security Settings -> Local Policies -> Audit Policy`

To access the advanced configuration go to\
`Computer Configuration -> Policies -> Windows Security Settings -> Advanced Audit Policy Configuration -> System Audit Policies`

From these locations you can choose things such as what events are logged, how to store and analyze data collected, set the maximum size of logs, and so on.

### Recommended - Audit Policy <a href="#recommended-audit-policy" id="recommended-audit-policy"></a>

A list of things it is recommended to monitor.

* monitor user logons
* directory service access
* account management
* object access
* logon events
* audit policy changes
* process tracking
* privlidge use

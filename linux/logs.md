# Logs

### Setting Up Logging <a href="#setting-up-logging" id="setting-up-logging"></a>

*   login.defs - log failed login attempts and home dir creation\
    path: `/etc/login.defs`

    `set FAILLOG_ENAB to yes`\
    `set CREATE_HOME to yes.`

### Common Logs to Watch <a href="#common-logs-to-watch" id="common-logs-to-watch"></a>

all in directory: `/var/log`

* auth.log or secure
* kern.log
* cron.log
* httpd (dir)
* nginx (dir)
* apt (dir)
* boot.log
* utmp, wtmp, btmp
* yum.log or dnf.log
* faillog

### systemd-journald <a href="#systemd-journald" id="systemd-journald"></a>

journalctl\
(`-u <service>` tag is optional and can be used to spescify services on any search)

* `journalctl -b` - boot message
* `journalctl -k -b -1` - kernal logs from prev boot
* `journalctl -f -u <service>` - logs by service
* `journalctl -f` - follow logs real time
* `journalctl /usr/bin/dbus-daemon` - dbus logs
* `journalctl /usr/local/bin/app` app executable logs
* `journalctl --since "30 min ago"` - by min
* `journalctl --since "1 hour ago"` - by hour
* `journalctl --since "1 days ago"` - by day
* `journalctl --since"YYYY-MM-DD HH:MM:SS` - since date or time
* `sudo journalctl _UID=<uid>` - by userID
* `sudo journalctl _PID=<PID>` - by PID

**Use -g flag to search journalctl with grep syntax**

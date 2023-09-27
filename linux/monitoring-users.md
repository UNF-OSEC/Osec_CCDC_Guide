# Monitoring Users

### W <a href="#w" id="w"></a>

tool to view info about currently logged in users

* `watch w` - view current users live
* `watch -i` - replaces from hostname with ip

### AC <a href="#ac" id="ac"></a>

prints statistics about connection times

* `ac -p` - print total login time of each user

### login logs <a href="#login-logs" id="login-logs"></a>

* `/var/log/wtmp` – Logs of last login sessions
* `/var/run/utmp` – Logs of the current login sessions
* `/var/log/btmp` – Logs of the bad login attempts

### Last <a href="#last" id="last"></a>

* `last` - view history of all successful logins to system
* `last <userName>` - view history of a spescific users logins
* `last -i` - display ip address of login history
* `last -<num>` - display the last x logins

### other <a href="#other" id="other"></a>

`lsof -u <username>` - list files open for x user

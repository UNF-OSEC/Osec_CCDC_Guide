# Processes

A process is a running instance of a program in Linux.

### Listing Processes <a href="#listing-processes" id="listing-processes"></a>

* list processes attatched to your terminal `ps`
* list all processes `ps aux`
* list resource hungry processes `top`
* list processes accessing a specific file `lsof <path>`
* list all files a process has open `lsof -p <pid>`
* list all processes in tree format `ps -auxwf`

atop and htop can also be installed to monitor processes\
use ps | grep to search processes

### Killing A Process <a href="#killing-a-process" id="killing-a-process"></a>

pid is found using ps command

* `kill -9 <pid>` - force kill process
* `kill <pid>` - nice way to kill process
* `killall <processName>` - kill process by name
* `pkill -f <processName>` - kill process by full name (use -9 to force)

***

It is good practice to check regularly for unknown processes.\
combine with `netstat`/`ss` & `lsof` to find processes communicating outside the system.

***

### Find the Location of a Process <a href="#find-the-location-of-a-process" id="find-the-location-of-a-process"></a>

* `pgrep <processName>` - get process id
* `pwdx <PID>` - find the present working directory of a process
* `ls -alhtr /proc/<PID>/fd/` or `lsof -p <PID>`- list open files by process
* `cd /proc/<PID>/cwd && pwd` - change directory to processes directory in /proc/
* `readlink /proc/<PID/cwd` - gives output of process symbolic link current working directory

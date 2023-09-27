# at

### Cron <a href="#cron" id="cron"></a>

cron is a system in linux to scheduel tasks\
cron is a service `cron.service` and can be dissabled

**Making Cronjobs**

Structure:

* edit crontab file `crontab -e`
* run at reboot `@reboot`
* structure: `[minute] [hour] [day of month] [month] [day of week] [command]`
* cron can be set to run scripts

[https://www.hostinger.com/tutorials/crontab-syntax](https://www.hostinger.com/tutorials/crontab-syntax)

**Checking For Cronjobs**

* display all cronjobs: `crontab -l` - run as root or w/ sudo
* list cronjobs for spescific user: `sudo crontab -u <userName> -l`
* view daily, hourly, or monthly cronjobs: `cd /etc/cron.<daily-hourly-yearly>/`\
  `ls -l`\
  `cat <fileName>`
* periodic: `cd /etc/periodic/<15min,hourly,daily,weekly,monthly>`\
  `ls -l`\
  `cat <fileName>`
* software specific cronjobs: `cd /etc/cron.d/`\
  `ls -l`\
  `cat <filename>`
* view all users cronjobs: `cat /var/spool/cron/crontabs/*`

***

timers are an alternative to cron using systemd

**Making Timers**

* create a file at `/etc/systemd/system/<file>.service`\
  bare minimum content
* create a timer file `~/.config/systemd/user/schedule-<name>.timer`
* `systemctl --user enable schedule-test.service`

Timer Resources\
[https://www.freedesktop.org/software/systemd/man/systemd.time.html#Calendar Events](https://www.freedesktop.org/software/systemd/man/systemd.time.html#Calendar%20Events)\
[https://fedoramagazine.org/systemd-timers-for-scheduling-tasks/](https://fedoramagazine.org/systemd-timers-for-scheduling-tasks/)

**Checking Timers**

* active timers: `systemctl list-timers`
* loaded but inactive timers: `systemctl list-timers –all`

***

### At <a href="#at" id="at"></a>

at is a utility to scheduel a one time command

**Running Commands With At**

* running scripts: `at <time> -f /path/to/sctipt.sh`
* running commands: `at <time>`\
  `<command>`

**Checking & deleting from at**

* list pending jobs: `at -l` or `atq`
* delet pending jobs: atrm `<job#>`

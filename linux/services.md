# Services

Services are programs that run in the background of Linux systems that are outside the normal control of users.

***

### Listing Services <a href="#listing-services" id="listing-services"></a>

you can determine your system manager, this will be the first process running in the pstree which can be seen with the command `pstree | head -n 5`

**For systemd / systemctl**

* `systemctl list-units --type=service`
* `systemctl list-units --type=service --all` lists all services
* `systemctl list-unit-files`\
  you can also specify running services with the flag `--state=running` (`state=active` also works), the `--type=service` flag spescifies services

It is also possible to search for specific services by piping the command to grep and specifying the service name\
e.x: `systemctl list-units --type=service | grep httpd`

### Checking the Status of Services <a href="#checking-the-status-of-services" id="checking-the-status-of-services"></a>

* `service --status-all | grep running`
* `chkconfig --list` list services enabeled on boot
* `initctl list` check services running in SystemV
* `systemctl status <serviceName>`

### Starting & Stopping Services <a href="#starting-stopping-services" id="starting-stopping-services"></a>

* `systemctl stop <service-name>`
* `systemctl disable <service-name>`
* `systemctl enable <service-name>`
* `systemctl start <service-name>`

### Editing Services <a href="#editing-services" id="editing-services"></a>

Systemd services can be modified using:\
`systemctl edit <name>.service`\
After editing they need to be restarted with:\
`systemctl restart <ServiceName>`

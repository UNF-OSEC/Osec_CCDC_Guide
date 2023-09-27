# Packages

For Debian based distros such as Ubuntu package manager is apt, for RHEL based such as centOS package manager is yum.

### Listing Installed Packages <a href="#listing-installed-packages" id="listing-installed-packages"></a>

`yum list installed` - rhel\
`apt list --installed` - deban

### Update Packages <a href="#update-packages" id="update-packages"></a>

`yum check update` - list updatable backages\
`yum update <package>` (spescific package is optional)\
`sudo apt list --upgradable` - list upgradable packages\
`apt --only-upgrade install <package>`\
`apt upgrade` - apt upgrade all packages

### Installing & Removing Packages <a href="#installing-removing-packages" id="installing-removing-packages"></a>

`apt install <package>`\
`apt remove <package>`\
`yum install <package>`\
`yum remove <package>`

### Updating the System <a href="#updating-the-system" id="updating-the-system"></a>

`sudo apt update`\
`$ sudo apt update && sudo apt upgrade -y` - both update and upgrade system\
`yum update`

# Bash

### Securing Bash <a href="#securing-bash" id="securing-bash"></a>

* lockdown .bashrc and .bash\_profile (in users home dir) using chattr `sudo chattr +i .bashrc` (use `-i` to undo this to edit the file).
* make and save a copy of your .bashrc and .bash\_profile

**Alias**\
An alias is a shortcut a user can set that refrences a command in the linux shell. the syntax is as follows\
`alias <option> <name>='<value>'`.

Temporary aliases that only persist for the terminal session can be set as `alias l='ls'`.

Permenant aliases are set in the .bashrc file in the users home directory. using `sudo nano ~./bashrc` you can edit the file and add an alias with the same syntax as above under the comment `#Custom aliases`.

**Detecting Aliases:**

* `cat ~./bashrc`
* `alias -p`
* `compgen -a`

**Running Commands If Bash is Damaged**

* `ssh <ip> 'bash --norc'` - use norc upon connect (`/bin/bash --norc` or `/bin/sh`) as command
* `ssh -T <ip>` `bash -i`
* log in as another user or root user
* use sftp or scp to overwrite bash with new uploaded `.bashrc`

***

### Bash History <a href="#bash-history" id="bash-history"></a>

* `cat /home/<user_name>/.bash_history` (if it hangs, type Ctrl+C)
* `tail /var/log/auth.log | grep username` - users sudo history
* `cat /root/.bash_history`
* `cat /var/log/<FILE>`
* `history` - list all commands run in terminal session

### Find the last time a command was run <a href="#find-the-last-time-a-command-was-run" id="find-the-last-time-a-command-was-run"></a>

``IFS=$'\n'; for hd in `getent passwd | cut -d: -f6`; do cat ${hd}/.*_history | grep <COMMAND>; done``

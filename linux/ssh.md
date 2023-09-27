# SSH

### Connecting to a System <a href="#connecting-to-a-system" id="connecting-to-a-system"></a>

*   To ssh into a system with a private key\
    `ssh -i /path/to/key/id_rsa -p <port#> <user>@x.x.x.x`\
    If you do not have a key yet exclude `-i /path/to/key/id_rsa`

    (`-p <port$>`` is optional unless port is not default`)\
    a domain can replace the IP if avaliable
* It is recommended to use a ssh client such as Bitvise or PuTTY

### Setting Up A New Key <a href="#setting-up-a-new-key" id="setting-up-a-new-key"></a>

After connecting to the system initially you should create a new ssh key, and set it up for use on the system.

1. Create the Key\
   `ssh-keygen -b 2048 -t rsa`\
   `-b` spescifies number of bytes, and `-t` the encryption type, `-f` can be used to specify file name such as `-f ~/.ssh/webServer.key`
2. You will be prompted to make a passphrase, this is not required but helps protect the key from unauthorized use
3. The default path to the keygen is\
   `/home/<username>/.ssh/id_rsa.`\
   (username may not be required)
4. Your public and private keys will show in the location above\
   \qquad\qquad- public: `id_rsa.pub`\
   \qquad\qquad- private: `id_rsa`
5. Move your public key to your remote machine\
   You can do this manually by simply moving the key into your `/.ssh` directory, or via from your machine you wish to connect from with the command `ssh-copy-id -i ~/.ssh/mykey <user>@x.x.x.x` using the ip of the machine you wish to copy the key to.
6. Test your key by attempting to ssh to the machine using `ssh -i ~/.ssh/mykey user@host`.

***

### Securing SSH <a href="#securing-ssh" id="securing-ssh"></a>

* Be sure to delete ssh keys that are unneeded or not used
* Disable Password SSH Login\
  open the sshd\_config file located at:\
  `sudo nano /etc/ssh/sshd_config`\
  make the following changes to to this file\
  `ChallengeResponseAuthentication no`\
  `PasswordAuthentication no`\
  `UsePAM no`\
  `PermitRootLogin no`\
  Now save the file and restart the ssh service.\
  For systemd linux systems: `sudo systemctl reload ssh`\
  For RHEL/CentOS systems: `/etc/init.d/sshd reload`

**To close inactive ssh sessions**\
`ClientAliveInterval 60`\
`ClientAliveCountMax 3`\
will send a message to clients every seconds, will do so three times and if it recieves no response the client will be dropped

**Changing the SSH Port**\
`#Port 22`\
edit to:\
`Port 2222`

**Monitor Login Fails**\
login.defs - log failed login attempts and home dir creation\
`/etc/login.defs`\
set `FAILLOG_ENAB` to yes\
set `CREATE_HOME` to yes. (this logs home directory creations)

* these display in `/var/log/faillog`

***

### Useful Tricks for SSH <a href="#useful-tricks-for-ssh" id="useful-tricks-for-ssh"></a>

* send a command upon connection\
  `ssh -t <user>@x.x.x.x '<command>; <command2>'`
* open a file to be edited upon connection\
  `ssh -t <user>@x.x.x.x nano /path/to/file`
* send files from host to vm
  * First connect via `sftp <username>@x.x.x.x`
  * Then use regular linux navigation commands to locate the file you wish to share `ls, pwd, cd`
  * Download files using the `get` command in sftp\
    `get /path/to/filename.zip`.
  * To save the file under a new name specify this name as the second argument.
  * to download a directory use the `-r` flag\
    `get -r /path/to/directory`
  * if a transfer fails use `reget /path/to/file`
  * to upload files from local machine use `put`\
    `put /local/file/path`
  * put usage is the same as get
  * You can make & remove directories, rename files, and change permissions the same as you normally would\
    \-to exit enter `quit` or `bye`

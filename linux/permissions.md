# Permissions



* Displaying user and group info
  * user: `cat /etc/passwd` displays users & privs
  * group: `cat /etc/group` displays all groups
* Deleting users and groups
  * `userdel -rf <username>`
  * `groupdel <groupname>`
* Adding users and groups
  * `groupadd <newGroupName>`
  * `useradd <userName>`
* Adding & Removing Users To Groups
  * `usermod -a -G <groupName> <userName>` - add
  * `deluser <user> <group>` - remove
* View Groups a User is In
  * `groups <userName>`

***

### Permissions <a href="#permissions" id="permissions"></a>

* u = owner
* g = group
* o = other
* a = all
* r = read
* w = write
* x = execute
* \- = not set\
  ex: `chmod u+rwx <file_name>` changes user permissions to read, write, and execute
* \+ adds permissions
* \- removes permissions
* \= sets level of access

**changing the owner**

* `chmod <user> <file/dir>`
* `chgroup <groupname> <file/dir>`
* `chown <user>:<group> <file>`

Ownership is used to set permissions,\
A file has an owner and a group, and you set permissions for those

To find backdoors, familiarize yourself with the list of files returned by `find / -type f -perm /6000 2>/dev/null` and compare against the files on the competition system

***

### FOR QUICK SETTING OF PERMISSIONS: <a href="#for-quick-setting-of-permissions" id="for-quick-setting-of-permissions"></a>

0 ---\
1 --x\
2 -w-\
3 -wx\
4 r--\
5 r-w\
6 rw-\
7 rwx

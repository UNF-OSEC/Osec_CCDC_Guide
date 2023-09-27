# Backups

This guide only covers linux backups using tar, there are many other ways to do them but this is the most common.

### What to Backup <a href="#what-to-backup" id="what-to-backup"></a>

list of directories to backup, stared with \* are most important

1. /etc \*
2. /home
3. /root \*
4. /var \*
5. /usr/local/bin
6. /usr/local/sbin
7. /srv
8. /opt \*
9.

### Creating Backups <a href="#creating-backups" id="creating-backups"></a>

* `tar -cvfz <backup_name>.tar </path/do/dir-or-file/` create a backup (remove the z to not compress backup)
* to exclude a file from backups add `--exclude <file>` before -`-cvf`

### Restoring Backups <a href="#restoring-backups" id="restoring-backups"></a>

* `# tar -xvpf </backup/to/restore>.tar.gz` restores the backup
* `tar tzf </backup/>.tar.gz` show files in backup
* `tar -xvfz <backupName>.tar.gz </backup/directory/file>` extracts the spescified file from the backup

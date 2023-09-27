# Partitions

**NFS**\
Installing nfs is slightly different depending if you are on a debian based system or not. For debian `sudo apt install nfs-common` while for RHEL based systems `sudo yum install nfs-utils`.

Once NFS is installed you are going to want to use it to mount a remote file system. Mount with the following command: `sudo mount -t nfs <IP>:/</mount/dir> </dir/to/mount/to>`. you can edit `/etc/fstab` to auto-mount. An example of its usage would be `10.10.0.10:/backups /var/backups nfs defaults 0 0`.

To unmount a share simply type `umount </dir/it/mounted/to>` spescifying the directory the remote file system resides in on your system.

***

**SSHFS**

Like NFS there are two different methods of installing SSHFS depending on your system. For debian based `sudo apt install sshfs` while for RHEL based `sudo yum install fuse-sshfs`.

Once it is installed you can mount a file system via ssh using the command `sudo sshfs [-o <options>] <remoteUser>@<remoteHost>:/<path to remote directory> /mnt/<folder name>/`\
Check the mount with `cd /mnt/<dirName>`.

To unmount the file system use `sudo umount /mnt/<dirName>`

***

### Partitions <a href="#partitions" id="partitions"></a>

To list current partitions on your filesystem use command `sudo fdisk -l`

After doing this we can select a disk to partition with `sudo fdisk [diskPath]`, after doing this enter command mode by typing `m` into the fdisk tool.

select `n` to create a new partition and `l` to make a logical partition.

select the sector of the partition, press enter for the first free sector then spescify its other bounds manually in the terminal. from here continue through the tool till the partition is made.

Once a partition is created its type will automatically be set to "Linux". To change this type `t` in fdisk and then enter the hex code for the type you want.

To view the final plan for the partition press `p`. If this is the partition you wish to make press `w` to write the new partition if not use `q` to quit.

Once you create a new partition it is recommended to format it. To do this type `sudo mkfs` then make the partition with the filesystem from mkfs that you like. For this example that is the ext4 filesystem: `sudo mkfs.ext4 [partitionPath]`

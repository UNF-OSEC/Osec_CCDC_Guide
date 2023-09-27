# Hashing Files

### File Hashing <a href="#file-hashing" id="file-hashing"></a>

Important files that are at risk of being modified should be hashed to give you method of checking if they have been altered.\
This can tell you when you should revert back to backups and serve as an indicator of compromise for the system.

There are two primary hashing algorythims used in linux. MD5 and SHA-256.

* To hash a file with MD5 use `md5sum </path/to/file>`
* To hash a file with SHA-256 `sha256sum </path/to/file>`

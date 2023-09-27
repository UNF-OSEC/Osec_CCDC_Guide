# RKHUNTER

clamAV is an opensource antivirus for linux

* install it via `sudo apt-get install clamav clamav-daemon`
* `sudo systemctl start clamav-freshclam` starts it as a service
* `sudo freshclam` updates virus signatures

**Usage**

* `-- infected` display infected files only
* `--remove` remove infected files
* `--recursive` scan subdirectories
* `--move` move infected files to spescific directory

example: `clamscan --infected --remove --recursive </dir/to/scan>`

***

### RKHUNTER <a href="#rkhunter" id="rkhunter"></a>

rkhunter is a tool that scans the system for rootkits, backdoors, and local exploits.

* `sudo apt install rkhunter` install the tool
* `sudo rkhunter --update` update tool signatures
* `sudo rkhunter --check --skip-keypress` run scan without user input

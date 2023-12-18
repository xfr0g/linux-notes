# Linux Fundamentals and Commands

Linux Filesystem Structure:
* /boot - contains file that is used by the boot loader (grub.cfg)
* /root - root user home directory.
* /dev - system devices (e.g. disk, cdrom, speakers, flashdrive, keyboard, etc.)
* /etc - configuration files
* /bin > /usr/bin - everyday user commands
* /sbin > /usr/sbin - system/filesystem commands
* /opt - optional add-on applications (not part of OS apps)
* /proc - running processes (only exist in memory)
* /lib > /usr/lib - C programming library files needed by commands and apps
* /tmp - directory for temporary files
* /home - directory for user
* /var - system logs
* /run - system daemons that start very early (e.g. systemd and udev) to store temporary runtime files like PID files
* /mnt - tomount external filesystem (e.g. NFS)
* /media - for cdrom mounts.

Linux File Types:
* (-) : regular file
* (d) : directory
* (l) : link
* (c) : special file or device file
* (s) : socket
* (p) : named pipe
* (b) : block device

What is Root?:
There are 3 types of root on Linux system:
* Root account: root is an account or a username on Linux machine and it is the most powerful account which has access to all commands and files.
* Root as /: the very first directory in Linux is also referred as root directory.
* Root home directory: the root user account also has a directory located in /root which is called root home directory.

Basic Commands:
* pwd - displays present working directory.
* ls - lists all files and directories.
* whoami - displays who you are logged in to.
* cd -  to change directory.

Create Files and Directories:
* touch <name>
* cp <name> <path>
* vim
* mkdir <name>

Find Files and Directories:
* find - iterates over a filesystem.
* locate - uses a prebuilt database.

Wildcards:
A wildcard is used to represent one or multiple characters.
* ( * ) - represents zero or more characters.
* ( ? ) - represents a single character.
* ( [] ) - represents a range of characters.
* ( {} ) - a brace expansion.
* ( ^ ) - anything that starts with the first character.
* ( $ ) - anything that ends with the last character.

File Permissions:
There are 3 types of permissions:
* r - read
* w - write
* x - execute

Numerical values:
* 0 - no permission
* 1 - execute
* 2 - write
* 3 - execute + write
* 4 - read
* 5 - read + execute
* 6 - read + write
* 7 - read + write + execute

Each permission can be controlled at three levels:
* u - user = yourself
* g - group = can be people in the same project
* o - other = everyone on the system
* a - all

Command to change permission:
* chmod

File Ownership:
* chrown - changes the ownership of a file.
* chgrp - changes the group ownership of a file.
* -R - changes all the ownership of the files within a directory.

Access Control List:
ACL provides an additional, more flexible permission mechanism for file systems. It is designed to assist with UNIX file permissions. ACL allows you to give permissions for any user or group to any disc resource.
Commands to assign and remove ACL permissions are:
setfacl
getfacl

List of commands for setting up ACL:
* To add permission for user
* setfacl -m u:user:rwx /path/to/file

* To add permissions for a group:
* setfacl -m g:group:rwx /path/to/file

* To allow all files or directories to inherit ACL entries from the directory it is within
* setfacl -Rm "entry" /path/to/dir

* To remove a specific entry
* setfacl -x u:user /path/to/file

* To remove all entries
* setfacl -b /path/to/file

Note: As you assign the ACL permission to a file/directory, it adds + sign at the end of the permission. And setting w permission with ACL does not allow to remove a file.

Help Commands:
There are 3 types of help commands:
* whatis <command>
* <command> --help
* man <command>

Adding Text to Files (Redirects):
3 Simple ways to add text to a file:
* vi
* Redirect command output > or >>
* echo > or >>

Input and Output Redirects:
There are 3 redirects in Linux:
* Standard Input (stdin) and it has file descriptor number as 0
* Standard Output (stdout) and it has file descriptor number as 1
* Standard Error (stderr) and it has file descriptor number as 2

Standard output to a file (tee):
tee command is used to store and view (both at the same time) the output of any command.

Pipes:
A pipe is used by the shell to connect the output of one command directly to the input of another command.
The symbol for a pipe is the vertical bar (|). The command syntax is:
* command1 <arguments> | command2 <arguments>

File Maintenance Commands:
* cp
* rm
* mv
* mkdir
* rmdir or rm -r
* chgrp
* chown

File Display Commands:
* cat
* more
* less
* head
* tail

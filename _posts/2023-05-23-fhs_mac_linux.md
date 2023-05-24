Refer - [Filesystem Hierarchy Standard](http://www.pathname.com/fhs/)

## Mac

| Directory | Description | users | depth | 
|------------|-------------|-------| ------|
| bin |  Essential command binaries | all users | no children |
| boot| Static files of the boot loader | |
| dev | Device files | |
| etc | Host-specific system configuration |
| lib | Essential shared libraries and kernel modules media Mount point for removeable media | |
| mnt | Mount point for mounting a filesystem temporarily opt Add-on application software packages | |
| sbin | Essential system binaries | |
| srv | Data for services provided by this system | |
| tmp | Temporary files | |
| usr | Secondary hierarchy var Variable data |shareable, readonly data |
| var | Variable data | contains variable data files. This includes spool directories and files, administrative and logging data, and transient and temporary files.|


### /bin

/bin - Binaries needed for normal/standard system functioning at any run level.

/usr/bin - Application/distribution binaries meant to be accessed by locally logged in users

There must be no subdirectories in /bin.

The following commands, or symbolic links to commands, are required in /bin.



| Command | Description| 
| --------| -----------|
| cat |Utility to concatenate files to standard output|
| chgrp | Utility to change file group ownership|
| chmod | Utility to change file access permissions|
| chown | Utility to change file owner and group
| cp |  Utility to copy files and directories
| date | Utility to print or set the system date and time 
| dd | Utility to convert and copy a file
| df | Utility to report filesystem disk space usage
|dmesg | Utility to print or control the kernel message buffer
| echo | Utility to display a line of text 
| false |  Utility to do nothing, unsuccessfully
| hostname | Utility to show or set the system’s host name
| kill |  Utility to send signals to processes
| ln | Utility to make links between files
| login | Utility to begin a session on the system
| ls | Utility to list directory contents
| mkdir | Utility to make directories
| mknod | Utility to make block or character special files
| more |  Utility to page through text
| mount | Utility to mount a filesystem
| mv | Utility to move/rename files
| ps | Utility to report process status
| pwd | Utility to print name of current working directory
| rm | Utility to remove files or directories
| rmdir | Utility to remove empty directories
| sed | The ‘sed’ stream editor
| sh | The Bourne command shell
| stty | Utility to change and print terminal line settings
| su | Utility to change user ID
| sync | Utility to flush filesystem buffers
| true |  Utility to do nothing, successfully
| umount | Utility to unmount file systems
| uname | Utility to print system information


### /var

The following directories, or symbolic links to directories, are required in /var.

| Directory | Description |
|-----------|-------------|
|cache | Application cache data |
|lib|  Variable state information |
|local|  Variable data for /usr/local|
|lock| Lock files |
|log|  Log files and directories |
|opt|  Variable data for /opt |
|run|  Data relevant to running processes |
|spool|  Application spool data |
| tmp | Temporary files preserved between system reboots |


------------------

## Linux 

#### / : Root directory
On Linux systems, if the kernel is located in `/`, we recommend using the names vmlinux or vmlinuz, which have been used in recent Linux kernel source packages.

### /bin : Essential user command binaries (for use by all users)
Linux systems which require them place these additional files into /bin:
• setserial

### /dev : Devices and special files
The following devices must exist under /dev.

`/dev/null`
All data written to this device is discarded. A read from this device will return an EOF condition.

`/dev/zero`
This device is a source of zeroed out data. All data written to this device is discarded. A read from this device will return as many bytes containing the value zero as was requested.

`/dev/tty`
This device is a synonym for the controlling terminal of a process. Once this device is opened, all reads and writes will behave as if the actual controlling terminal device had been opened.

 ### /etc : Host-specific system configuration
Linux systems which require them place these additional files into /etc.
• lilo.conf

### /proc : Kernel and process information virtual filesystem
The proc filesystem is the de-facto standard Linux method for handling process and system information, rather than /dev/kmem and other similar methods. We strongly encourage this for the storage and retrieval of process information as well as other kernel and memory information.

### /sbin : Essential system binaries
Linux systems place these additional files into /sbin.



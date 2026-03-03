

Urraca Backup Tool (urracabt)
===========================
---------------------------
[Léalo en Español](https://github.com/DDaniel993/Urraca-backup-tool/blob/main/Requeriments_and_install_es.md)

Requirements and Installation
-----------------------------

Urracabt is written in Python, version 3.12.3. It uses standard Python 
libraries such as tkinter, threading, shutil, or glob, all included in 
Python’s standard library. If Python is installed on your system — as 
is usually the case in most modern GNU/Linux distributions — no 
additional software needs to be installed.

Due to its simplicity, there is no installer. Simply download it as a 
compressed package or clone it. You can place it wherever additional 
software not part of the system is typically located — i.e., /opt or 
/usr/local. The former is recommended by the FHS (Filesystem Hierarchy 
Standard) for this type of software.

You don’t need to keep the root directory name; you may rename it to 
something more meaningful or familiar to you. The application links to 
the assets/ and locales/ subdirectories but does not depend on an absolute
path to the root directory. The screenshots/ subdirectory is used on servers
to display interface previews but is not required on your machine.

On first run, you must select the language, then fill in the source 
directories and files, the destination, and any desired options.

Save your changes with a descriptive name for your backup. These settings 
are saved in the file you defined and in a hidden file called .urracabt.conf, 
which should not be edited manually. Similarly, do not manually edit the 
configuration file you created; if you need different parameters for a backup 
type other than your original, modify the fields in the graphical interface
and save it under a new name reflecting the new purpose.







 




Urraca Backup Tool (urracabt)
===========================
---------------------------
[Léalo en Español](https://github.com/DDaniel993/Urraca-backup-tool/blob/main/README_es.md))

Urracabt is a graphical user interface for creating backups based on the `rsync`
command in GNU/Linux. While `rsync` can also run on Windows, Ubtool uses certain
GNU/Linux system commands via Python subprocesses, making it incompatible with
Windows.

![Principal.jpg](/screenshots/principal.jpg)

The goal of Urracabt is to simplify the use of rsync through a graphical 
user interface. It allows managing copy processes locally (e.g., external
disk drives) as well as remotely. In the latter case, access can be achieved
via password or public key through SSH. Urracabt does not manage the creation 
of private/public keys or their sharing with a remote server; this must be
done independently by the user or system administrator.

---


Synchronization Options
-----------------------

### Default Options (Transparent to the User)

	Some rsync options are included by default. For example, preserving 
	original file attributes is considered good practice.

	* The -a option ensures symbolic links, permissions, and file
	  ownership are preserved.

	* The -P option includes two flags:
	  --progress displays transfer progress during synchronization.
  	  --partial allows partially transferred files to be retained if 
	  the copy is interrupted, enabling resumption later.  
  
*Note: Following `rsync` recommendations, Ubtool does not allow stopping a 
copy process once started. Thus, `--partial` is useful only if the program
crashes or is interrupted unexpectedly.*

	* The `-v` (verbose) option provides real-time output during copying,
      helping verify the process is proceeding as intended. All this information
	  is displayed live in a process log window.

These options are hardcoded into the program and are transparent to the user, 
but can be modified by editing the Python source code.

### User Options

	Urracabt provides configurable options shown on the main screen, which
	are self-explanatory:

	- Preserve symbolic links of files.
	- Copy the linked file (follow symlinks).
	- Delete destination file if it no longer exists in the source.
	- Compress during copy. This does not produce compressed final
      backup files — it compresses data during transfer to reduce time, 
	  especially useful for remote backups.

---

## Multiple Configurations

	Different configurations can be managed to meet user needs — for example,
	maintaining a local copy and a second copy on a remote server. Each 
	configuration is stored in a separate, easily accessible config file 
	via the menu.

---

## Cron Scheduler

	Cron jobs can be generated automatically using parameters from the
    current configuration.	The	tool also checks whether a cron job already
	exists in the cron file, preventing duplicates.

![programador_cron.jpg](/screenshots/programador_cron.jpg)

---

## Languages

	A dropdown menu in the menu bar allows switching between Spanish and English.

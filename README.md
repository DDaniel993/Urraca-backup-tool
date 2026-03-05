# Urraca Backup Tool (urracabt)

[Léalo en Español](https://github.com/DDaniel993/Urraca-backup-tool/blob/main/README_es.md)

Urraca Backup Tool (urracabt) is a graphical user interface for creating backups based on the `rsync` command on GNU/Linux systems. Although `rsync` can also run on Windows, urracabt relies on GNU/Linux system commands via Python subprocesses — making it incompatible with Windows.

## Features

- Graphical interface for `rsync`
- Local and remote backups (via SSH)
- Customizable sync options
- Multiple configuration profiles
- Built-in cron scheduler
- Language support: Spanish and English

![Principal.jpg](/screenshots/principal.jpg)

It supports managing backup processes locally (e.g., external drives) as well as on remote locations. In the latter case, access can be established via password or public key authentication over SSH. Note: **urracabt does not manage the creation or distribution of SSH key pairs** — this must be handled independently by the user or system administrator.

---

## Sync Options

### Default Options (Transparent to the User)

Some `rsync` options are included by default, as they are considered best practices for preserving file integrity:

- `-a`: Preserves symbolic links, permissions, ownership, and other attributes.
- `-P`: Combines two flags:
  - `--progress`: Shows real-time transfer progress.
  - `--partial`: Keeps partially transferred files if the copy is interrupted, allowing resumption later.
  
  > ⚠️ **Note**: Urracabt does not allow stopping a backup once started (following `rsync`’s own recommendations). Thus, `--partial` is useful in case of unexpected interruptions.

- `-v` (verbose): Provides detailed output during the copy process, helping users verify that everything proceeds as expected. All output is displayed in real time in the activity log window.

These options are hardcoded into the program and are transparent to the user — but can be modified by editing the Python source code.

### User Options

Urracabt offers the following configurable options, displayed on the main screen:

- **Preserve symbolic links** — Keeps symbolic links as links.
- **Copy linked file** — Copies the actual file pointed to by the link.
- **Delete on destination if missing in source** — Removes files from the destination that no longer exist in the source.
- **Compress during transfer** — Compresses data *during* transfer to reduce time (especially useful for remote backups). Note: Final files are **not** compressed.

---

## Multiple Configurations

You can manage different backup configurations to suit your needs — for example, keeping one local copy and another on a remote server. Each configuration is saved in a separate, easily accessible file via the menu.

---

## Cron Scheduler

Urracabt can generate and install cron jobs using the parameters from the current configuration. It also checks for existing entries to avoid duplicates in the user’s crontab.

![programador_cron.jpg](/screenshots/programador_cron.jpg)

---

## Languages

A language selector in the menu bar lets you switch between **Spanish** and **English**.

---

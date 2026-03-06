# Urraca Backup Tool (urracabt)

![Lealo en Español](https://github.com/DDaniel993/Urraca-backup-tool/blob/main/README_es.md)

> **Graphical interface for backups with `rsync` on GNU/Linux**

Urraca Backup Tool (urracabt) is a graphical application for creating backups based on the `rsync` command, specifically designed for GNU/Linux systems. Although `rsync` also works on Windows, urracabt depends on Linux system commands, so **it is not compatible with Windows**.

![Principal](/screenshots/principal_en.jpg)

---

## 🛠️ Features

- Intuitive graphical interface for rsync
- Local (external drives) and remote (SSH) backups
- Customizable synchronization options
- Management of multiple configurations
- Integrated cron scheduler

![Cron Scheduler](/screenshots/programador_cron_en.jpg)

- Language support: Spanish and English
- Optional password encryption: When using password authentication (instead of SSH public key), urracabt locally encrypts the password using the `cryptography` library.

---

## 🚀 Installation

### For end users

```bash
# Install from PyPI (coming soon) or from .whl file
pip install urracabt

# Or install locally from .whl
pip install dist/urracabt-1.4.2-py3-none-any.whl

# Run the app
urracabt
```

### For developers
```bash

# Clone the repo
git clone https://github.com/tu-usuario/urracabt.git
cd urracabt

# Set up virtual environment
python -m venv urraca_packager
source urraca_packager/bin/activate  # Linux/macOS

# Install dependencies
pip install -r requirements.txt

# Install in dev mode
pip install -e .

# Launch app
urracabt
```


## 🌐 Basic Usage

- 1 Open urracabt from terminal or applications menu.
- 2 Select backup type: local or remote.
- 3 Configure source, destination, and options.
- 4 Click Start rsync.



## 🔐 Security & Encryption
When using password authentication (instead of SSH key), urracabt encrypts the password locally using the cryptography library before saving it to the config file — preventing plain-text exposure.

🔐 Note: Encryption is local-only. It does not encrypt transferred files. For file-level encryption, use tools like gpg or cryptsetup.

## 📁 Project Structure

![Structure](/screenshots/estructura_proyecto.jpg)

## 🤝 Contributions

We welcome contributions! Here’s how:


Fork the repository.

1 Create a new branch:
```bash
$ git checkout -b feature/your-feature-name
```

2 Commit your changes:
```bash
$ git commit -am 'Add new feature'
```
3 Push to your branch:
```bash
$ git push origin feature/your-feature-name
```
4 Open a Merge Request.


## 📄 License
This project is licensed under GPL v3.

## 📬 Support
Found a bug? Have a suggestion?
👉 Open an Issue or send a message.

Thank you for using Urraca Backup Tool! 🐦💾


---

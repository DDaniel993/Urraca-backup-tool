
# Urraca Backup Tool (urracabt)

> **Graphical interface for backups using `rsync` on GNU/Linux**

![Léalo en Español](README_es.md)

Urraca Backup Tool (urracabt) is a graphical application for creating backups based on the `rsync` command, specifically designed for GNU/Linux systems. Although `rsync` also works on Windows, urracabt relies on Linux system commands, so **it is not compatible with Windows**.

![Main Interface](/screenshots/principal_es.jpg)

---

## 🛠️ Features

- Intuitive graphical interface for rsync
- Local (external drives) and remote (SSH) backups
- Customizable sync options
- Management of multiple configurations
- Built-in cron scheduler

![Cron Scheduler](/screenshots/programador_cron_es.jpg)

- Language support: Spanish and English
- Optional password encryption: When using password authentication (instead of SSH public key), urracabt locally encrypts the password using the `cryptography` library.

---

## 🚀 Installation

### For end users

```bash
# Install from PyPI or .whl file
pip install urracabt

# Or install locally from .whl
pip install dist/urracabt-1.4.2-py3-none-any.whl

# Run the application
urracabt
```

### For developers

```bash
# Clone the repository
git clone https://github.com/tu-usuario/urracabt.git
cd urracabt

# Set up virtual environment
python -m venv urraca_packager
source urraca_packager/bin/activate  # Linux/macOS

# Install dependencies
pip install -r requirements.txt

# Install in development mode
pip install -e .

# Launch the application
urracabt
```
---

## 🌐 Basic Usage

- 1 Open urracabt from terminal or application menu.
- 2 Select backup type: local or remote.
- 3 Configure source, destination, and options.
- 4 Click Start.
---

## 🔐 Security and Encryption
When using password authentication (instead of SSH key), urracabt locally encrypts the password using the cryptography library before saving it to the config file — preventing exposure in plain text.

🔐 Note: Encryption is local only. It does not encrypt transferred files. For file-level encryption, use tools like gpg or cryptsetup.

---

## 🤝 A few important things before you begin

### 🛠️ The `.urracabt.conf` file
This is a hidden file created and managed by the app to handle configurations. 

**Please do not edit it manually** — it may break the app’s functionality.

### 🔐 And if you use a password for remote backups...
A secret file named .secret.key is generated.
This file acts as the master key protecting your password.

> 💡 **If you move the app to another location...**
> Don’t forget to move it there too!
> If you don’t, the app won’t be able to decrypt your password, and you’ll 
> need to create a new one.

---

## 📄 License
This project is licensed under GPL v3.

---

## 📬 Support
Found a bug? Have a suggestion? 👉 Open an Issue or send a message.
Thanks for using Urraca Backup Tool! 🐦💾
If you have questions, we’re here to help.


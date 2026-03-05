# Urraca Backup Tool (urracabt)

> **Interfaz gráfica para copias de seguridad con `rsync` en GNU/Linux**

Urraca Backup Tool (urracabt) es una aplicación gráfica para crear copias de seguridad basadas en el comando `rsync`, diseñada específicamente para sistemas GNU/Linux. Aunque `rsync` también funciona en Windows, urracabt depende de comandos del sistema Linux, por lo que **no es compatible con Windows**.

![Principal.jpg](/screenshots/principal_es.jpg)

---
## 🛠️ Características  
- Interfaz gráfica intuitiva para rsync
- Copias locales (discos externos) y remotas (SSH)
- Opciones de sincronización personalizables
- Gestión de múltiples configuraciones
- Programador cron integrado

![programador_cron_es.jpg](/screenshots/programador_cron_es.jpg)

- Soporte para idiomas: Español e Inglés
- Cifrado opcional de contraseñas: Cuando se usa autenticación por 
  contraseña (en lugar de   clave pública SSH), urracabt encripta la 
  contraseña localmente usando la biblioteca cryptography.
---

## 🚀 Instalación

### Para usuarios finales
```
Instala urracabt desde PyPI (próximamente) o desde el archivo `.whl` generado:

- $ pip install urracabt

O, si tienes el archivo .whl localmente:

- $ pip install dist/urracabt-1.4.2-py3-none-any.whl

Luego, ejecuta la aplicación desde la terminal:

- $ urracabt
```

### Para desarrolladores
```
Clona el repositorio:

- $ git clone https://github.com/tu-usuario/urracabt.git
- $ cd urracabt

Crea y activa un entorno virtual:

- $ python -m venv urraca_packager
- $ source urraca_packager/bin/activate (Linux)

Instala las dependencias:

- $ pip install -r requirements.txt

Instala el paquete en modo desarrollo:

- $ pip install -e .

Ejecuta la app:

- $ urracabt

```
---


## 🌐 Uso básico

- 1 Abre urracabt desde la terminal o el menú de aplicaciones.

- 2 Selecciona el tipo de copia: local o remoto.

- 3 Configura origen, destino y opciones.

- 4 Inicia la copia.

---

## 🔐 Seguridad y encriptado
Cuando se utiliza autenticación por contraseña (en lugar de clave pública SSH), urracabt encripta la contraseña localmente usando la biblioteca cryptography antes de guardarla en el archivo de configuración. Esto evita que la contraseña quede expuesta en texto plano.

🔐 Nota: La encriptación es local y solo protege la contraseña en el archivo de configuración. No cifra los datos de copia ni los archivos transferidos. Para cifrado de archivos, se recomienda usar herramientas adicionales como gpg o cryptsetup.

---

## 📁 Estructura del proyecto
urracabt/

├── README.md                  # Documentación principal
├── requirements.txt           # Dependencias para desarrolladores
├── setup.py                   # Configuración del paquete
├── urracabt/
│   ├── __init__.py
│   ├── urracabt.py            # Código principal
│   ├── assets/                # Imágenes
│   └── locales/               # Archivos de traducción
└── .gitignore                 # Archivos a ignorar en Git

## 🤝 Contribuciones

¡Bienvenidas! Si deseas contribuir:

Haz un fork del repositorio.
Crea una rama nueva:
 
   git checkout -b feature/nombre

Haz tus cambios y commítalos: git commit -am 'Añade nueva funcionalidad'
Sube la rama: git push origin feature/nombre
Abre un Pull Request.
---

## 📄 Licencia
Este proyecto está bajo la licencia GPL. v.3

---
## 📬 Soporte
Si tienes problemas o sugerencias, abre un issue en el repositorio o envíame un mensaje.

¡Gracias por usar Urraca Backup Tool! 🐦💾

---
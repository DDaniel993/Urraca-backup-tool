# Herramienta de Copia de Seguridad Urraca (urracabt)

> **Interfaz gráfica para copias de seguridad con `rsync` en GNU/Linux**

Urraca Backup Tool (urracabt) es una aplicación gráfica para crear copias de seguridad basadas en el comando `rsync`, diseñada específicamente para sistemas GNU/Linux. Aunque `rsync` también funciona en Windows, urracabt depende de comandos del sistema Linux, por lo que **no es compatible con Windows**.

![Principal](/screenshots/principal_es.jpg)

---

## 🛠️ Características

- Interfaz gráfica intuitiva para rsync
- Copias de seguridad locales (unidades externas) y remotas (SSH)
- Opciones de sincronización personalizables
- Gestión de múltiples configuraciones
- Programador cron integrado

![Programador Cron](/screenshots/programador_cron_es.jpg)

- Soporte de idiomas: Español e Inglés
- Cifrado de contraseña opcional: Al usar autenticación por contraseña (en lugar de clave pública SSH), urracabt cifra localmente la contraseña utilizando la biblioteca `cryptography`.

---

## 🚀 Instalación

### Para usuarios finales

```bash
# Instalar desde PyPI o desde archivo .whl
pip install urracabt

# O instalar localmente desde .whl
pip install dist/urracabt-1.4.2-py3-none-any.whl

# Ejecutar la aplicación
urracabt
```

### Para desarrolladores
```bash
# Clonar el repositorio
git clone https://github.com/tu-usuario/urracabt.git
cd urracabt

# Configurar entorno virtual
python -m venv urraca_packager
source urraca_packager/bin/activate  # Linux/macOS

# Instalar dependencias
pip install -r requirements.txt

# Instalar en modo desarrollo
pip install -e .

# Lanzar la aplicación
urracabt
```
---

## 🌐 Uso Básico
- 1 Abrir urracabt desde la terminal o menú de aplicaciones.
- 2 Seleccionar tipo de copia de seguridad: local o remota.
- 3 Configurar origen, destino y opciones.
- 4 Hacer clic en Iniciar.
---

## 🔐 Seguridad y Cifrado
Al usar autenticación por contraseña (en lugar de clave SSH), urracabt cifra la contraseña localmente utilizando la biblioteca cryptography antes de guardarla en el archivo de configuración — evitando exposición en texto plano.

🔐 Nota: El cifrado es solo local. No cifra los archivos transferidos. Para cifrado a nivel de archivo, utiliza herramientas como gpg o cryptsetup.

---

## 🤝 Un par de cosas importantes antes de empezar

### 🛠️ El archivo `.urracabt.conf` 
Es un fichero oculto que la app crea y maneja para gestionar las configuraciones.  
**Por favor, no lo edites a mano**  
Si lo modificas, podría alterarse su funcionamiento.

### 🔐 Y si usas contraseña para copias remotas...

Se genera un archivo secreto llamado `.secret.key` 
Este archivo es como la llave maestra que protege tu contraseña.  

> 💡 **Si mueves la app a otro lugar...**  
> ¡No olvides llevarlo al nuevo destino !  
> Si no lo haces, la app no podrá descifrar tu contraseña y tendrás que crear una nueva.  

---

## 📄 Licencia
Este proyecto está licenciado bajo GPL v3.

---

## 📬 Soporte
¿Encontraste un error? ¿Tienes una sugerencia? 👉 Abre un Issue o envía un mensaje.
¡Gracias por usar Urraca Backup Tool! 🐦💾
Si tienes dudas, estamos aquí para ayudarte.

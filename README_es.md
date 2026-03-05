

Urraca Backup Tool (urracabt)
===========================


Urracabt es una interface gráfica de usuario para crear copias de
seguridad basada en el comando rsync en Gnu/Linux. El comando rsync
también puede ejecutarse en un sistema Windows pero urracabt hace
uso de algunos comandos del sistema Gnu/Linux a través de subprocesos
en el lenguaje Python por lo que no sería posible usar esta utilidad
en este sistema.

## Características

- Interfaz gráfica para `rsync`
- Copias locales y remotas (via SSH)
- Opciones de sincronización personalizables
- Gestión de múltiples configuraciones
- Programador cron integrado
- Soporte para idiomas: Español e Inglés
- **Cifrado opcional de contraseñas**: Cuando se usa autenticación por contraseña (en lugar de clave pública SSH), urracabt encripta la contraseña localmente usando la biblioteca `cryptography` para protegerla en el archivo de configuración.

![Principal.jpg](/screenshots/principal.jpg)


Tiene la posibilidad de gestionar procesos
de copia de forma local (ej: unidades de discos externos) así como en
emplazamientos remotos. En este caso, es posible acceder mediante una
contraseña o una llave pública para la conexión a través de ssh.
Urracabt no gestiona la creación de llaves privadas/públicas ni la
compartición de estas llaves con un servidor remoto, esto debe hacerlo
el usuario o administador del sistema de forma independiente.


---


Opciones de sincronización
--------------------------

### Opciones por defecto (Transparentes al usuario)  


Algunas opciones del comando rsync están añadidas por defecto. Por ejemplo,
se ha considerado como una buena práctica mantener los atributos originales
de los archivos que se copian. 

- La opción `-a` en el comando rsync asegura que los enlaces
  simbólicos, permisos y  propietario de los ficheros sean preservados.
 
- La opción `-P` en el comando rsync incluye dos flags:
  - `--progress` muestra el progreso durante la sincronización y
    `--partial` que permite mantener archivos parcialmente transferidos
	  si la copia se interrumpe para poder reanudar después. 

> ⚠️ **Note**: Ubtool no  permite, atendiendo a las recomendaciones
	   propias de rsync, detener un proceso de copia una vez que este
       ha sido iniciado. Por tanto, el flag --partial sería útil en
       casos en los que algún problema hiciese discontinuar la
       ejecución del programa.


- La opción -v (verbose), proporciona  información de salida durante
  el proceso de copia, lo que ayudará a comprobar que todo se desarrolla
  de la forma que se desee. Toda esa información puede leerse en tiempo
  real en una ventana de log de la actividad de los procesos.


Estas opciones están incluídas en el código del programa y resultan
transparentes al usuario, pero podrían modificarse editando el código en
el lenguaje Python.



### Opciones de Usuario

Urracabt cuenta con opciones para la ejecución que se muestran en la
pantalla principal y se explican por sí mismas:

- **Conservar enlaces simbólicos de los archivos.**

- **Copiar el archivo enlazado.**

- **Borrar fichero en destino si ese fichero ha dejado de existir en
  origen.**

- **Comprimir durante la copia.** Esta opción no produce ficheros de copia
      finales comprimidos. Comprime los datos durante la copia para
      disminuir el tiempo empleado en esta. Puede ser útil en procesos
      remotos.

---

Múltiples configuraciones
-------------------------

Pueden gestionarse diferentes configuraciones para cubrir las
necesidades del usuario. Por ejemplo, mantener una copia de los archivos
y directorios de forma local y una segunda copia en un servidor remoto.
Cada una de ella es almacenada en un archivo de configuración
independiente y fácilmente accesible a través del menú.

---

Programador cron
----------------

Pueden construirse órdenes para cron que serán enviadas automáticamente
usando los parámetros especificados en la configuración actual. Además
se comprueba que una orden enviada a cron no exista en el archivo de
cron, evitando así duplicados en las órdenes.

![programador_cron.jpg](/screenshots/programador_cron.jpg)

---

Idiomas
-------

En la barra de menús existe un desplegable que permite seleccionar entre
el idioma Español y el Inglés.

---
## Seguridad y encriptado

Cuando se utiliza autenticación por **contraseña** (en lugar de clave pública SSH), urracabt encripta la contraseña localmente usando la biblioteca `cryptography` antes de guardarla en el archivo de configuración. Esto evita que la contraseña quede expuesta en texto plano.

> 🔐 **Nota**: La encriptación es local y protege la contraseña en el archivo de configuración. 

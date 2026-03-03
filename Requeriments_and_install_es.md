

Urraca Backup Tool (urracabt)
===========================
---------------------------

Requerimientos e instalación
-------------------------------

Urracabt está escrito en el lenguaje Python, en su versión 3.12.3.
Usa librerías como tkinter, threading, shutl o glob, todas incluídas
en la biblioteca standard de Python. Si tiene Python instalado en
su sistema, como normalmente ocurre en casi todas las distribuciones
GNU/Linux actuales, no será necesario que instale nada accesorio. 

Dada su simplicidad no existe un instalador, simplemente descárguelo
como paquete comprimido o clonándolo. Puede ubicarlo donde normalmente
se suelen ubicar el software adicional que no forma parte del sistema,
es decir /opt o /usr/local. El primero es el recomendado por el
FHS (Filesystem Hierarchy Standard) para este tipo de software.

No es necesario que respete el nombre del directorio raíz; puede llamarlo
de otra forma que le sea más significativa o familiar. La aplicación
enlaza con los subdirectorios assets/ y locales/ pero no depende de una 
ruta absoluta al el directorio raíz. Por otra parte, el subdirectorio
screenshots/ se ubica en los servidores para mostrar una imagen del
aspecto del interfaz pero no es necesario que exista en su equipo.

En la primera ejecución debe elegir el idioma y, posteriormente rellenar
los campos de los directorios y ficheros de origen y el de destino así
como las opciones que desee de las que están disponibles.

Guarde los cambios asignando un nombre descriptivo para su copia de seguridad.
Estos cambios se guardan en el fichero que ha definido y en un fichero oculto
llamado .urracabt.conf que no es recomendable editar manualmente. Tampoco
se recomienda editar manualmente el fichero de configuración que ha creado;
si necesita otros parámetros para un tipo de copia diferente al que ha 
creado inicialmente, realice los cambios sobreescribiendo los campos en
la interfaz gráfica y guardelo con un nombre distinto que haga referencia
a el nuevo cometido de la copia.









 



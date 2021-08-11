
## Primero lo primero... ¿Qué es la consola del sistema operativo?

La consola, la interfaz de comandos o la línea de comandos, es una interfaz que nos permite enviar **comandos** a nuestro sistema operativo por medio de una línea de texto.

Pero, ¿porqué es importante conocer la consola? Nos permite **mayor control** sobre el sistema operativo y las aplicaciones, nos permite **ejecutar un conjunto de comandos** para automatizar tareas (scripts) y utilizamos **menos recursos** del sistema operativo (memoria, cpu).

Ya sea que utilices **Windows, Linux o Mac**, aquí vamos con una introducción básica a los comando que utilizaremos, pero recuerda, la consola es muy potente y tendrás cientos de comandos que nos pueden resultar útiles.

Comencemos por los archivos y carpetas, nuestro sistema operativo nos permite manipular una estructura jerárquica donde organizamos nuestros archivos en directorios o carpetas:

### Listar archivos
Para ver un listado de los archivos en una carpeta, podemos utilizar el comando **ls** (linux) o **dir** (Windows) y veremos como resultado el lista de archivos en la carpeta actual.

### Rutas (absolutas y relativas)
Una ruta, es una ubicación dentro de nuestro sistema de archivos. Por ejemplo:

 - En linux (o Mac), /home/usuario/Desktop/prog2.txt es una **ruta absoluta** al archivo prog2.txt que se encuentra en la carpeta /home/usuarioUCU/Desktop.
 - En Windows, las carpetas están ubicadas, además, en unidades de disco, así que una ruta absoluta podría ser c:\Users\usuarioUCU\Desktop\prog2.txt.

Ya habrás notado que linux utiliza el símbolo **/** para la estructura de carpetas y Windows utiliza el símbolo **\** (aunque Windows lo entiende de ambas formas).

¿Y las rutas relativas? Bueno, las rutas relativas están determinadas por la ubicación que tengamos dentro del sistema de archivos cuando ejecutamos un comando. Así que si estamos trabajando en la carpeta c:\Users\usuarioUCU\Desktop y ejecutamos ejecutamos el comando **dir**, obtendremos la lista de archivos en esa ubicación, pero si ejecutamos el comando **"dir  . ."** entonces tendremos el lista de la carpeta de nivel superior. No importa donde nos ubiquemos, siempre **". ."** (sin espacios entre los puntos) hará referencia a la carpeta de nivel superior. Ya habrás intentado qué pasa cuando ponemos **"dir . .\ . . "**, sí, tenemos el lista de los archivos 2 niveles arriba de la ubicación actual.

Lo mismo pasa con los archivos, **". .\prog2.txt"** hace referencia a un archivo de nombre prog2.txt que se encuentra en una carpeta superior. ¿Superior a quién?, superior a la carpeta donde nos encontremos actualmente.

Pero, ¿esto de las rutas absolutas es solo para Windows? No, es análogo en Linux (o Mac) pero con el comando **ls**. El comando **ls** nos permite obtener la lista de archivos del directorio actual, **"ls . . "** la del directorio de nivel superior y **"ls . ./. ."** son dos niveles superiores.

### Cambio de directorio
Ahora necesitamos movernos en el sistema de archivos y eso lo hacemos con el comando **cd**. Esto por surte, funciona igual en todos los sistema operativos. Así que si estamos en linux ubicado en la carpeta /home/usuarioUCU y queremos ubicarnos en la carpeta "Desktop" de nivel inverior, ejecutaremos **"cd Desktop"** y ahora estamos en la carpeta que también llamamos hija. Claro, con **cd . .** volvemos a ubicarnos en la carpeta padre.

Es probable que muchas veces te sientas confundido al no saber en qué directorio o carpeta nos encontramos. Muy bien, Windows te lo dirá con el comando **cd** y Linux con el comando **pwd**

### Creando y borrando
Me gustaría crear un nuevo directorio. No hay problema **mkdir** (Windows, Linux, Mac) seguido por un nombre adecuado nos permite hacerlo. La nueva carpeta se crea en la ubicación actual, es decir será una carpeta hija.

¿Y si quiere borrar?  Ya sea que estemos borrando un archivo o una carpeta, **rmdir** (Windows, Linux, Mac) seguido por el nombre del recurso a borrar nos permite eliminar **definitivamente** el mismo.


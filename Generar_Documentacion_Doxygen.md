## Comandos para generar documentación utilizando Doxygen

Antes de generar la documentación del proyecto es necesario crear un archivo de configuración de Doxygen. Para ello, nos pararemos en la raiz de nuestra solución (repositorio), y crearemos primero una carpeta que almacene toda nuestra documentación (si no existe aún).

1 - Crear `docs/`

![windows](./assets/gh-windows.svg)
```bash
mkdir docs
```
Linux/Mac
md docs

2 - Inicializamos Doxygen dentro de docs/

```bash
cd docs
Doxygen -g
```
Esto crea un archivo de configuración llamado `Doxyfile` con una configuración predenterminada.

3 - Modificamos el archivo de configuración de Doxygen de la siguiente forma: abrir ```docs/Doxygen``` y editar las siguientes líneas:

```diff
...
--PROJECT_NAME           = "My Project"
++PROJECT_NAME           = "<nombre de tu proyecto>"
...
--OPTIMIZE_OUTPUT_JAVA   = NO
++OPTIMIZE_OUTPUT_JAVA   = YES
...
--RECURSIVE              = NO
++RECURSIVE              = YES
...
```
Puedes descargar [este archivo Doxyfile](https://github.com/ucudal/PII_ProjectTemplate/blob/master/docs/Doxyfile) que ya tiene todas las modificaciones.

4 - Ejecutamos Doxygen

```bash
Doxygen
```

5 - Para ver la documentación abrir en un navegador web:

```bash
docs/index.html
```
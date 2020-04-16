# Comandos para crear un repositorio GIT
## FIT
### Universidad Católica del Uruguay

0 - Navegamos hasta el directorio donde crearemos el repositorio

`cd <directorio>`

1 - Creamos el repositorio git

`git init`

2 - Creamos un archivo .gitignore. Puedes copiar uno de otro proyecto, o descargar [este](https://github.com/dotnet/core/blob/master/.gitignore).

_*[L/M]*_  `touch .gitignore`

_*[W]*_  `echo $null >> .gitignore`

Agregar el contenido del .gitignore manualmente.

3 - Creamos un archivo README.md

_*[L/M]*_  `touch README.md`

_*[W]*_  `echo $null >> README.md`

4 - Agregar un remoto. Esto es, vincular un repositorio local a uno remoto (en GitHub por ejemplo)

`git remote add origin <url del remoto>`

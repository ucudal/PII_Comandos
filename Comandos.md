# Comandos para crear un proyecto de C#
## PII - FIT
### Universidad Católica del Uruguay

A continuación se detallan los comandos para crear proyectos de C# con la estructura base que utilizaremos en el curso.

Estructura base
--------

0 - Creamos una carpeta para nuestro proyecto. Cambiar "proyecto" por un nombre adecuado

`mkdir proyecto`

1 — Navegamos a la carpeta creada en el paso 0.

`cd proyecto`

2 — Creamos una carpeta src para nuestros proyectos de C#

`mkdir src`

3 — Navegamos a la carpeta src

`cd src`

4 — Creamos un proyecto nuevo de consola llamado Program

`dotnet new console -n Program`

5 — Creamos un proyecto nuevo de biblioteca llamado Library

`dotnet new classlib -n Library`

6 - Creamos un proyecto nuevo de test (NUnit) llamado Library.Test

`dotnet new nunit -n Library.Test`

7 - Navegamos al proyecto de consola (Program) y agregamos una referencia al proyecto de biblioteca (Library)

`cd Program`
`dotnet add Program.csproj reference ../Library/Library.csproj`

8 — Navegamos al proyecto de test (Library.Test) y agregamos una referencia al proyecto de biblioteca (Library)

`cd ../Library.Test`
`dotnet add Library.Test.csproj reference ../Library/Library.csproj`


Al final de estos pasos, deberías tener en el directorio de tu proyecto la siguiente estructura:

```
src/
    Program/
        Program.csproj
    Library/
        Library.csproj
    Library.Test/
        Library.Test.csproj
```

Repositorio
--------

0 — Si nos encontramos parados en Library.Test (luego del paso 8), navegamos a la raiz de nuestro proyecto

`cd ../..`

1 - Inicializamos un repositorio git

`git init`

2 - Creamos un archivo .gitignore. Podemos copiar uno de otro proyecto, o utilizar [este](https://github.com/dotnet/core/blob/master/.gitignore).


README
--------

Recomendamos siempre incluír un archivo README.md en la raiz del proyecto.
# Comandos para crear un proyecto de C#
## FIT
### Universidad Católica del Uruguay

A continuación se detallan los comandos para crear proyectos de C# con la estructura base que utilizaremos en el curso.

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

6 - Navegamos al proyecto de consola (Program) y agregamos una referencia al proyecto de biblioteca (Library)

`cd Program`
`dotnet add Program.csproj reference ../Library/Library.csproj`

7 - Navegamos hacia atrás, nuevamente a src/

`cd ..`

8 - Creamos un directorio Test para los proyectos de test.

`mkdir Test`

9 - Creamos un proyecto nuevo de test (NUnit) llamado Library.Test dentro del directorio Test.

`cd Test`
`dotnet new nunit -n Library.Test`

10 — Navegamos al proyecto de test (Library.Test) y agregamos una referencia al proyecto de biblioteca (Library)

`cd Library.Test`
`dotnet add Library.Test.csproj reference ../../Library/Library.csproj`


Al final de estos pasos, deberías tener en el directorio de tu proyecto la siguiente estructura:

```
src/
    Program/
        Program.csproj
    Library/
        Library.csproj
    Test/
        Library.Test/
            Library.Test.csproj
```
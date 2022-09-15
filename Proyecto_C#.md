## Comandos para crear un proyecto de C#


A continuación se detallan los comandos para crear proyectos de C# con la estructura base que utilizaremos en el curso.

0 - Creamos una carpeta para nuestro proyecto. Cambiar "proyecto" por un nombre adecuado

```bash
mkdir proyecto
```

1 — Navegamos a la carpeta creada en el paso 0.

```bash
cd proyecto
```

2 — Creamos una carpeta src para nuestros proyectos de C#

```bash
mkdir src
```

3 — Navegamos a la carpeta src

```bash
cd src
```

4 — Creamos un proyecto nuevo de consola llamado Program

```bash
dotnet new console -n Program
```

5 — Creamos un proyecto nuevo de biblioteca llamado Library

```bash
dotnet new classlib -n Library
```

6 - Navegamos al proyecto de consola (Program) y agregamos una referencia al proyecto de biblioteca (Library)

```bash
cd Program
dotnet add Program.csproj reference ../Library/Library.csproj
```

7 - Navegamos hacia atrás, hasta la carpeta "proyecto"

```bash
cd ..
cd ..
```

8 - Creamos un directorio Test para los proyectos de test.

```bash
mkdir Test
```

9 - Creamos un proyecto nuevo de test (NUnit) llamado Library.Test dentro del directorio Test.

```bash
cd Test
dotnet new nunit -n Library.Test
```

10 — Navegamos al proyecto de test (Library.Test) y agregamos una referencia al proyecto de biblioteca (Library)

```bash
cd Library.Test
dotnet add Library.Test.csproj reference ../../src/Library/Library.csproj
```


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

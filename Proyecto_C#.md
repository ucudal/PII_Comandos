## Comandos para crear un proyecto de C#

A continuación se detallan los comandos para crear proyectos de C# con la estructura base que utilizaremos en el curso.

0 – Creamos una carpeta para nuestro proyecto. Cambiar `proyecto` por el nombre que corresponda.

```bash
mkdir proyecto
```

1 – Navegamos a la carpeta creada en el paso 0.

```bash
cd proyecto
```

2 - Crear una solución. La solución contendrá referencias a todos nuestros demás proyectos.

```bash
dotnet new sln
```

3 – Creamos las carpetas:
- src: Para los proyectos donde escribiremos nuestro código.
- docs: Para proyecto de documentación.
- test: para proyecto de testing.

```bash
mkdir src
mkdir docs
mkdir test
```

4 — Navegamos a la carpeta `src`.

```bash
cd src
```

5 — Creamos un proyecto nuevo de consola llamado `Program`. Este proyecto tendrá nuestro programa principal.

```bash
dotnet new console -n Program --use-program-main
```

6 — Creamos un proyecto nuevo de librería llamado `Library`. Este proyecto tendrá nuestras clases.

```bash
dotnet new classlib -n Library
```

7 - Navegamos al proyecto de consola `Program` y agregamos una referencia al proyecto de librería `Library`. Esto es para que el programa principal pueda usar las clases que creemos en las librerías.

```bash
cd Program
dotnet add Program.csproj reference ../Library/Library.csproj
```

8 - Navegamos hacia atrás, hasta la carpeta `proyecto`.

```bash
cd ..
cd ..
```

9 - Creamos un proyecto nuevo de test (NUnit) llamado `Library.Tests` dentro del directorio test.

```bash
cd test
dotnet new nunit -n Library.Tests
```

10 — Navegamos al proyecto de test `LibraryTests` y agregamos una referencia al proyecto de biblioteca `Library`. Esto es para que nuestros tests puedan acceder a las clases que creemos en las librerías.

```bash
cd Library.Tests
dotnet add Library.Tests.csproj reference ../../src/Library/Library.csproj
```

11 - Volver al directorio raíz del proyecto

```bash
cd ..
cd ..
```

12 - Agregar los tres proyectos creados a la solución.

```bash
dotnet sln add src/Library/Library.csproj
dotnet sln add src/Program/Program.csproj
dotnet sln add test/Library.Tests/Library.Tests.csproj
```

13 - Generar archivo .gitignore
```bash
dotnet new gitignore
```

Al final de estos pasos, deberías tener en el directorio de tu proyecto la siguiente estructura de directorios:

```
src/
    Program/
        Program.csproj
    Library/
        Library.csproj
test/
     Library.Tests/
     Library.Tests.csproj
```

También podríamos crear un .bat que contenga todos los comandos mencionados anteriormente y agregarlo a la variable path para que lo podamos ejecutar dentro de cualquier carpeta de proyecto previamente creada. Hasta puedo hacer que me abra code.

```bash
dotnet new sln
mkdir src
mkdir docs
mkdir test
cd src
dotnet new console -n Program --use-program-main
dotnet new classlib -n Library
cd Program
dotnet add Program.csproj reference ../Library/Library.csproj
cd ..
cd ..
cd test
dotnet new nunit -n LibraryTests
cd LibraryTests
dotnet add LibraryTests.csproj reference ../../src/Library/Library.csproj
cd ..
cd ..
dotnet sln add src/Library/Library.csproj
dotnet sln add src/Program/Program.csproj
dotnet sln add test/LibraryTests/LibraryTests.csproj
dotnet new gitignore
code .
```

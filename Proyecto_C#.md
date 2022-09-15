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

2 - Creamos las carpetas:   
- src: Para el proyecto Library y proyecto Program
- docs: Para proyecto de documentación  
- test: para proyecto de testing.

```bash
mkdir src
mkdir docs
mkdir test
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

8 - Creamos un proyecto nuevo de test (NUnit) llamado LibraryTests dentro del directorio test.

```bash
cd test
dotnet new nunit -n LibraryTests
```

9 — Navegamos al proyecto de test (LibraryTests) y agregamos una referencia al proyecto de biblioteca (Library)

```bash
cd LibraryTests
dotnet add LibraryTests.csproj reference ../../src/Library/Library.csproj
```

10 - Volver al directorio raíz del proyecto

```bash
cd ..
cd ..
```

11 - Crear solución

```bash
dotnet new sln
```

12 - Agregar los tres proyectos creados a la solución.

```bash
dotnet sln add src/Library/Library.csproj
dotnet sln add src/Program/Program.csproj
dotnet sln add test/LibraryTests/LibraryTests.csproj
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
     LibraryTests/
     LibraryTests.csproj
```


También podríamos crear un .bat que contenga todos los comandos mencionados anteriormente y agregarlo a la variable path para que lo podamos ejecutar dentro de cualquier carpeta de proyecto previamente creada. Hasta puedo hacer que me abra code.

```bash
mkdir src
mkdir docs
mkdir test
cd src
dotnet new console -n Program
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
dotnet new sln
dotnet sln add src/Library/Library.csproj
dotnet sln add src/Program/Program.csproj
dotnet sln add test/LibraryTests/LibraryTests.csproj
dotnet new gitignore
code .
```

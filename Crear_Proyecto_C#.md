## Comandos para crear un proyecto de C#

A continuación se detallan los comandos para crear proyectos de C# con la
estructura base que utilizaremos en el curso.

> [!TIP]
> Elijan una carpeta en su disco para guardar todos los proyectos de este curso.
> Conozcan la ruta a esa carpeta y sepan cómo llegar a ella desde la consola.

Mira cómo abrir la consola [aquí](./Consola.md#cómo-iniciar-la-consola)



En C# vamos a trabajar con diferentes proyectos. Cada proyecto va en su propia carpeta. La estructura de carpetas que vamos a crear es la siguiente:

```
  docs/
    ...
  src/
    Program/
      ...
    Library/
      ...
  test/
    Library.Tests/
      ...
```

En la carpeta `docs` vamos a generar la documentación de nuestro código. No te preocupes, no vas a tener que escribir la misma documentación dos veces, vamos a generarla automáticamente a partir de comentarios que incluyas en el código más adelante. Mientras no te hayamos mostrado cómo generar la documentación, puedes omitir esta carpeta. :warning: Cuidado, cuando te pidamos que generes documentación, no podrás omitir esa carpeta.

En la carpeta del proyecto hay dos carpetas, `src` y `test`. En `src` está el código de nuestras clases del proyecto. En `test` está el código de las clases de prueba. En caso de que tu proyecto no tenga clases de prueba, puedes omitir la carpeta `test`. :warning: Cuidado, cuando te pidamos que hagas casos de prueba, no podrás omitir esa carpeta.

En la carpeta `src` hay dos carpetas, `Library` y `Program`. En `Library` pondremos el proyecto –un proyecto de librería– y el código de todas las clases que use nuestro programa principal. En `Program` pondremos el proyecto –que típicamente es un proyecto de consola– y el código del programa principal que usa las demás clases.

En la carpeta `test` hay una carpeta `Library.Test`. En esta carpeta estará el proyecto de prueba y las clases de prueba de las que programemos en `Library`. Habrá una clase de prueba por cada clase en `Library`.

:question: ¿Por qué es necesaria esta estructura de carpetas? En un programa muy sencillo, no es necesaria; en programas más complejos, habrá muchas clases, y para que sea fácil encontrarlas, es mejor saber dónde buscarlas.

A continuación te daremos paso a paso los comandos que debes ejecutar en la línea de comandos o la terminal para crear esta estructura de carpetas y los respectivos proyectos.

0 – Creamos una carpeta para nuestro proyecto. Cambiar `proyecto` por el nombre que corresponda. Este comando tenemos que ejecutarlo en la carpeta donde guardamos todos nuestros proyectos; te mostramos más arriba cómo llegar a ella.

```bash
mkdir proyecto
```

1 – Nos movemos a la carpeta creada en el paso 0. Esto es para simplificar los comandos que siguen, porque no tendremos que decirles en qué carpeta se ejecutan, sino que asumirán la carpeta actual.

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

4 — Navegamos a la carpeta `src`. De nuevo, esto es para simplificar los comandos que siguen, que asumen que la carpeta en la que se ejecutan es la carpeta actual.

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

10 — Navegamos al proyecto de test `Library.Tests` y agregamos una referencia al proyecto de biblioteca `Library`. Esto es para que nuestros tests puedan acceder a las clases que creemos en las librerías.

```bash
cd Library.Tests
dotnet add Library.Tests.csproj reference ../../src/Library/Library.csproj
```

11 - Volver al directorio raíz del proyecto

```bash
cd ..
cd ..
```

12 - Agregar los tres proyectos creados a la solución. Esto es para poder compilar todos nuestros proyectos de una sola vez.

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
docs/
src/
    Program/
        Program.csproj
    Library/
        Library.csproj
test/
     Library.Tests/
        Library.Tests.csproj
```

También podríamos crear un .bat que contenga todos los comandos mencionados anteriormente y agregarlo a la variable path para que lo podamos ejecutar dentro de cualquier carpeta de proyecto previamente creada. Hasta puedo hacer que me abra Visual Studio Code.

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
dotnet new nunit -n Library.Tests
cd Library.Tests
dotnet add Library.Tests.csproj reference ../../src/Library/Library.csproj
cd ..
cd ..
dotnet sln add src/Library/Library.csproj
dotnet sln add src/Program/Program.csproj
dotnet sln add test/Library.Tests/Library.Tests.csproj
dotnet new gitignore
code .
```
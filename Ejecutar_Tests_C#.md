## Ejecutar tests C#


0 - Navegar a la raiz del proyecto de test. Asumimos que el proyecto tiene la estructura base del curso. Cambiar `Library.Test` por el nombre del proyecto de test.

```bash
cd test/Library.Test
```

Allí debe existir un con extensión ".csproj".

1 - Compilar el proyecto

```bash
dotnet build
```

Esto nos dará información sobre advertencias y errores.

2 - Ejecutar el proyecto

```bash
dotnet test
```

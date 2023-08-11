## Comandos para crear un repositorio GIT


0 - Navegamos hasta la carpeta donde crearemos el repositorio, típicamente la carpeta raíz donde está nuestro proyecto. Cambiar `proyecto` por el nombre que corresponda.

```bash
cd proyecto
```

1 - Creamos el repositorio git

```bash
git init
```

2 - Creamos un archivo .gitignore adecuado para proyectos C#. Puedes descargar [este](https://github.com/dotnet/core/blob/master/.gitignore) o usar el comando:

```bash
dotnet new gitignore
```

3 - Creamos un archivo README.md

![mac](./assets/gh-mac.svg)  ![linux](./assets/gh-linux.svg)
```bash
touch README.md
```

![windows](./assets/gh-windows.svg)
```bash
echo $null >> README.md
```

4 - Agregar un remoto. Esto es, vincular un repositorio local a uno remoto (en GitHub por ejemplo)

```bash
git remote add origin <url del remoto>
```
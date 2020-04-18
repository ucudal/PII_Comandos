## Comandos para crear un repositorio GIT


0 - Navegamos hasta el directorio donde crearemos el repositorio

```bash
cd <directorio>
```

1 - Creamos el repositorio git

```bash
git init
```

2 - Creamos un archivo .gitignore. Puedes copiar uno de otro proyecto, o descargar [este](https://github.com/dotnet/core/blob/master/.gitignore).

![mac](./assets/gh-mac.svg)  ![linux](./assets/gh-linux.svg)  
```bash
touch .gitignore
```

![windows](./assets/gh-windows.svg)  
```bash
echo $null >> .gitignore
```

Agregar el contenido del .gitignore manualmente.

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

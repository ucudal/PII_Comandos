## Comandos para generar documentación utilizando DocFx

Antes de generar la documentación del proyecto es necesario crear un archivo de configuración de DocFx. Para ello, nos pararemos en la raiz de nuestra solución (repositorio), y crearemos primero una carpeta que almacene toda nuestra documentación (si no existe aún).

1 - Crear `docs/`

```bash
mkdir docs
```

2 - Inicializamos docfx dentro de docs/

```bash
cd docs
docfx init -q
```
Esto crea una carpeta llamada `docfx_project` dentro de `docs/`.

3 - Modificamos el archivo de configuración de docfx para que encuentre nuestros proyectos dentro de `src/`. Abrir docs/docfx_project/docfx.json y editar las siguientes líneas:

```diff
{
  "metadata": [
    {
      "src": [
        {
          "files": [
--          "src/**.csproj"
++          "**/**.csproj"
--        ]
++        ],
++        "src": "../../src"
        }
      ],
      "dest": "api",
      "disableGitFeatures": false,
      "disableDefaultFilter": false
    }
  ],
  "build": {
    "content": [
      {
        "files": [
          "api/**.yml",
          "api/index.md"
        ]
      },
      {
        "files": [
          "articles/**.md",
          "articles/**/toc.yml",
          "toc.yml",
          "*.md"
        ]
      }
    ],
    "resource": [
      {
        "files": [
          "images/**"
        ]
      }
    ],
    "overwrite": [
      {
        "files": [
          "apidoc/**.md"
        ],
        "exclude": [
          "obj/**",
          "_site/**"
        ]
      }
    ],
    "dest": "_site",
    "globalMetadataFiles": [],
    "fileMetadataFiles": [],
    "template": [
--    "default"
++    "statictoc"
    ],
    "postProcessors": [],
    "markdownEngineName": "markdig",
    "noLangKeyword": false,
    "keepFileLink": false,
    "cleanupCacheHistory": false,
    "disableGitFeatures": false
  }
}
```

4 - Ejecutamos docfx

```bash
cd ..
docfx docs/docfx_project/docfx.json
```

5 - Para ver la documentación en el navegador web:

```bash
docfx docs/docfx_project/docfx.json --serve
```

Luego, visitar el siguiente link: http://localhost:8080

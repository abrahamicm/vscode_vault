# Snippet a nivel de proyecto 

1. **Creación del archivo de snippet de proyecto:**
   - En tu proyecto, crea un directorio llamado `.vscode` en la raíz (si no existe).
   - Dentro de `.vscode`, crea un archivo con extensión `.code-snippets`. Por ejemplo, `project-snippets.code-snippets`.

2. **Definición del snippet en el archivo del proyecto:**
   - Abre el archivo `project-snippets.code-snippets` y agrega el siguiente contenido:

```json
{
  "console log": {
    "scope": "javascript",
    "prefix": "clog",
    "body": [
      "console.log('$1');",
      "$2"
    ],
    "description": "Log to console"
  }
}
```

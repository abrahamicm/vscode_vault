**Tutorial de PHP CodeSniffer (PHPCS)**


### Paso 1: Instalación

1. **Instalación global de PHP CodeSniffer:**

   ```bash
   composer global require "squizlabs/php_codesniffer=*"
   ```

```bash
phpcs  -l --standard=PSR2 . 
# Verificar un archivo usando el estándar PSR2
phpcs --standard=PSR2 archivo.php

# Verificar varios archivos y directorios, ignorando ciertos patrones, usando el estándar PSR2
phpcs --standard=PSR2 --ignore=vendor/,tests/ --standard=PSR2 directorio1/ archivo1.php archivo2.php

# Mostrar lista de estándares de codificación instalados
phpcs -i

# Establecer un valor de configuración específico de php.ini (en este caso, aumentar el límite de memoria)
phpcs -d memory_limit=256M directorio/ --standard=PSR2

# Mostrar progreso de la ejecución en un directorio, usando el estándar PSR2
phpcs --standard=PSR2 -p directorio/

# Ejecutar en modo silencioso (sin salida detallada)
phpcs -q archivo.php

# Ignorar ciertos archivos y directorios usando patrones, con el estándar PSR2
phpcs --standard=PSR2 --ignore=vendor/,tests/ directorio/

# Generar un informe en formato JSON en un directorio, con el estándar PSR2
phpcs --standard=PSR2 --report=json --report-file=informe.json directorio/

# Ejemplo 9: Mostrar información sobre un estándar de codificación específico
phpcs -e PSR12

# Ejemplo 10: Explicar un estándar mostrando los olfateos que incluye
phpcs -e PSR2

```

| Opciones                   | Descripción                                                   |
|---------------------------|---------------------------------------------------------------|
| -n                        | No imprimir advertencias (atajo para --warning-severity=0)    |
| -w                        | Imprimir tanto advertencias como errores (valor predeterminado)|
| -l                        | Solo directorio local, sin recursividad                        |
| -s                        | Mostrar códigos de olfateo en todos los informes              |
| -a                        | Ejecutar de forma interactiva                                  |
| -e                        | Explicar un estándar mostrando los olfateos que incluye        |
| -p                        | Mostrar progreso de la ejecución                               |
| -q                        | Modo silencioso; desactiva la salida de progreso y la salida detallada|
| -m                        | Detener la grabación de mensajes de error (ahorra memoria, pero impide que se utilicen muchos informes)|
| -v                        | Imprimir archivos procesados                                   |
| -vv                       | Imprimir reglas y salida de tokens                             |
| -vvv                      | Imprimir información de procesamiento de olfateo               |
| -i                        | Mostrar una lista de estándares de codificación instalados     |
| -d                        | Establecer el valor [clave] de php.ini en [valor] o [true] si se omite el valor|
| --help                    | Imprimir este mensaje de ayuda                                 |
| --version                 | Imprimir información de versión                                |
| --colors                  | Utilizar colores en la salida                                   |
| --no-colors               | No utilizar colores en la salida (predeterminado)              |
| --cache                   | Almacenar en caché los resultados entre ejecuciones            |
| --no-cache                | No almacenar en caché los resultados entre ejecuciones (predeterminado)|
| --ignore-annotations      | Ignorar todas las anotaciones phpcs: en los comentarios de código|
| \<cacheFile>               | Utilizar un archivo específico para la caché (utiliza un archivo temporal de forma predeterminada)|
| \<basepath>                | Una ruta para eliminar del principio de las rutas de archivo dentro de los informes|
| \<bootstrap>               | Una lista separada por comas de archivos para ejecutar antes de que comience el procesamiento|
| \<encoding>                | La codificación de los archivos que se están verificando (el predeterminado es utf-8)|
| \<extensions>              | Una lista separada por comas de extensiones de archivo para verificar|
|                           | El tipo de archivo se puede especificar utilizando: ext/tipo   |
|                           | p. ej., modulo/php,es/js                                        |
| \<file>                    | Uno o más archivos y/o directorios para verificar              |
| \<fileList>                | Un archivo que contiene una lista de archivos y/o directorios para verificar (uno por línea)|
| \<filter>                  | Utilice el filtro "gitmodified" o "gitstaged", o especifique la ruta a una clase de filtro personalizada|
| \<generator>               | Utilice el generador "HTML", "Markdown" o "Text" (obliga a la generación de documentación en lugar de verificar)|
| \<patterns>                | Una lista separada por comas de patrones para ignorar archivos y directorios|
| \<processes>               | Cuántos archivos se deben verificar simultáneamente (el predeterminado es 1)|
| \<report>                  | Imprimir ya sea el informe "full", "xml", "checkstyle", "csv"|
|                           | "json", "junit", "emacs", "source", "summary", "diff"         |
|                           | "svnblame", "gitblame", "hgblame" o "notifysend", o especifique la ruta a una clase de informe personalizada|
|                           | (el informe "full" se imprime de forma predeterminada)         |
| \<reportFile>              | Escribir el informe en la ruta de archivo especificada         |
| \<reportWidth>             | Cuántas columnas de ancho deben imprimirse los informes de pantalla|
|                           | o establezca "auto" para usar el ancho de pantalla actual, donde sea compatible|
| \<severity>                | La gravedad mínima requerida para mostrar un error o advertencia|
| \<sniffs>                  | Una lista separada por comas de códigos de olfateo para incluir o excluir de la verificación|
|                           | (todos los olfateos deben ser parte del estándar especificado)  |
| \<standard>                | El nombre o la ruta del estándar de codificación a utilizar    |
| \<stdinPath>               | Si se procesa STDIN, la ruta del archivo que se procesará como STDIN|
| \<tabWidth>                | El número de espacios que representa cada tabulación           |


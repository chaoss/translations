# Licencia declarada

Pregunta: ¿Cuáles son las licencias declaradas del paquete de software?

## Descripción
El número total y las licencias específicas declaradas en un paquete de software. Esto puede incluir archivos fuente de software y documentación. Esta métrica es una enumeración de licencias y la cantidad de archivos con esa declaración de licencia en particular. Por ejemplo:

| Tipo de licencia de SPDX | Número de archivos con licencia |
| ------------------------ | ------------------------------- |
| MIT                      | 44                              |
| AGPL                     | 2                               |
| Apache                   | 88                              |


## Objetivos
El número total y las licencias específicas declaradas es fundamental en varios casos:
1. La invariabilidad de un paquete de software conlleva múltiples licencias de software y es fundamental en la adquisición de paquetes de software estar al tanto de las licencias declaradas por razones de cumplimiento. Las licencias declaradas pueden proporcionar transparencia para los esfuerzos de cumplimiento de licencias.
2. Las licencias pueden crear conflictos de modo que no se puedan cumplir todas las obligaciones en todas las licencias de un paquete de software. Las licencias declaradas pueden proporcionar transparencia sobre posibles conflictos de licencias presentes en los paquetes de software.

## Implementación

### Filtros
* Tiempo: las licencias declaradas en un repositorio pueden cambiar con el tiempo a medida que cambian las dependencias del repositorio. Una de las principales motivaciones para rastrear la presencia de licencias, además del conocimiento básico, es llamar la atención sobre cualquier introducción inesperada de una nueva licencia.
* Declarada y no declarada: enumeración separada de archivos que tienen declaraciones de licencia y archivos que no las tienen.

### Herramientas que proporcionan la métrica

 1. [Augur](https://github.com/chaoss/augur)

 Las licencias declaradas se pueden encontrar en cualquier [página de riesgo de Augur](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk) en la sección «Licencia declarada».

 2. [Augur-SPDX](https://github.com/chaoss/augur-spdx)

El paquete Augur-SPDX se implementa como un complemento de Augur y utiliza este modelo de datos para almacenar información de licencia a nivel de archivo. Específicamente:
* Cada `paquete` (repositorio) puede tener una licencia declarada y no declarada, según lo determinado por el escaneo de todos los archivos en el repositorio.
* Cada `paquete` también puede tener una serie de `documentos` distintos del código, que son declaraciones de licencia SPDX.
* Cada `archivo` se puede asociar con uno o más `packages_files`. A través de la relación entre `archivos` y `packages_files`, Augur-SPDX permite la posibilidad de que un archivo en una gran colección de repositorios pueda ser parte de más de un paquete, aunque en la práctica esto parece poco probable.
* Los `paquetes` y `packages_files` tienen una relación de uno a muchos en ambas direcciones. Esencialmente, esto es un refuerzo de la posibilidad de que cada `archivo` pueda ser parte de más de un `paquete`, aunque, nuevamente, es típico que cada `paquete` contenga muchos `package_files`.
* Las `licencias` están asociadas con `archivos` y `packages_files`. Cada `archivo` podría tener posiblemente más de una referencia de `licencias`, lo cual es posible bajo la condición de que la declaración de `licencias` cambie entre escaneos de `Augur-SPDX` del repositorio. Cada `paquete` se almacena en su forma más reciente, y cada `packages_file` puede tener una declaración de `licencia`.

## Referencias
* https://spdx.org/
* https://www.fossology.org

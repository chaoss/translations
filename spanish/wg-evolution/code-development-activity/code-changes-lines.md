# Líneas de cambios de código

Pregunta: ¿Cuál es la suma de la cantidad de líneas tocadas (líneas añadidas más líneas eliminadas) en todos los cambios al código fuente durante un período determinado?


## Descripción

Al introducir cambios en el código fuente, los desarrolladores tocan (editar, añadir, eliminar) líneas de los archivos del código fuente. Esta métrica considera el número agregado de líneas tocadas por cambios en el código fuente realizados durante un período determinado. Esto significa que si una línea determinada en un archivo determinado se toca en tres cambios diferentes, contará como tres líneas. Dado que en la mayoría de los sistemas de administración de código fuente es difícil o imposible decir con precisión si una línea fue eliminada y luego añadida, o simplemente editada, consideraremos que editar una línea es como eliminarla y luego añadirla con un nuevo contenido. Cada una de esas acciones (eliminar y añadir) se considerará como «tocar». Por lo tanto, si una línea determinada en un archivo determinado se edita tres veces, contará como seis cambios diferentes (tres eliminaciones, y tres añadidos).

Para ello, consideramos los cambios en el código fuente tal y como se define en [Cambios de código](https://github.com/chaoss/wg-evolution/blob/master/metrics/Code_Changes.md). Las líneas de código serán cualquier línea de un archivo de código fuente, incluidos los comentarios y las líneas en blanco.


## Objetivos

* Volumen de la actividad de codificación:  
  Aunque los cambios de código pueden ser un indicador de la actividad de codificación de un proyecto, no todos los cambios son iguales. Teniendo en cuenta que el número agregado de líneas tocadas en todos los cambios da una idea complementaria del tamaño de los cambios, y en general, del tamaño del volumen de codificación actividad.


## Implementación

**Agregadores:**
* Cantidad. El número total de líneas de cambios (tocadas) durante el período.

**Parámetros:**
* **Período de tiempo:** Fecha de inicio y finalización del período. Por defecto: para siempre.  
  Período durante el cual se consideran los cambios.<br>
* **Criterios para el código fuente; Algoritmo predeterminado:**  todos los archivos son código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si un archivo es parte del código fuente o no.<br>
* **Tipo de cambio de código fuente:**
    - Líneas añadidas
    - Líneas eliminadas
    - Espacio en blanco


### Filtros

* Por actores (autor, committer). Requiere la fusión de actores (fusionar identificadores correspondientes al mismo autor).

* Por grupos de actores (empleador, género...). Requiere agrupación de actores, y probablemente, fusión de actores.

* Por [etiquetas](https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name) (utilizadas en el mensaje de los commits). Requiere una estructura para el mensaje de commits. Esta etiqueta se puede utilizar en un proyecto de código abierto para comunicar a todos los contribuyentes si el commit es, por ejemplo, una corrección de un error o una mejora de una función.

## Visualizaciones

* Cantidad por mes a lo largo del tiempo
* Cantidad por grupo a lo largo del tiempo

Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría cambios de código durante un período determinado (por ejemplo, un mes).


### Herramientas que proporcionan la métrica

* [GrimoireLab](https://chaoss.github.io/grimoirelab) proporciona esta métrica lista para usar.
  - Vea un ejemplo de en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/f13af0e0-18e5-11e9-ba47-d5cbef43f8d3).
  - Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/chaoss-gmd-cde/lines_of_code_changed/).
  - Añada una visualización de muestra a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree un nuevo gráfico de `Área`
    * Seleccione el índice `git`
    * Eje Y 1: Agregación `Suma`, Campo `lines_added`, Etiqueta personalizada `Líneas añadidas`
    * Eje Y 2: Agregación `Suma`, Campo `painless_inverted_lines_removed_git`, Etiqueta personalizada `Líneas eliminadas`
    * Eje X: Agregación `Histograma de fechas`, Campo `grimoire_creation_date`, Intervalo `Automático`, Etiqueta personalizada `Hora`
  - Captura de pantalla de ejemplo: ![Captura de pantalla de GrimoireLab de la métrica Code_Changes_Lines](images/code-changes-lines_grimoirelab.png)


### Estrategias de recopilación de datos

**Descripción específica: Git**

En los casos de git, definimos «cambio de código» y «fecha de un cambio» como detallamos en [Cambios de código](https://github.com/chaoss/wg-evolution/blob/master/metrics/Code_Changes.md). La fecha de un cambio se puede definir (para considerarlo en un período o no) como la fecha del autor o la fecha del committer del commit de git correspondiente.

Dado que git proporciona cambios como parches de diferencias (lista de líneas añadidas y eliminadas), cada una de esas líneas mencionadas como una línea añadida o una línea eliminada en la diferencia se considerará como una línea modificada (tocada). Si se quita y se añade una línea, se considerará como dos «cambios en una línea».

__Parámetros obligatorios:__

* Tipo de fecha. La fecha del autor o la fecha del committer. Por defecto: fecha del autor.  
  Para cada commit de git, se conservan dos fechas: cuándo se creó el commit y cuándo se efectuó el commit en el repositorio. Para decidir el período, se debe seleccionar uno de ellos.<br>

* Incluir los commits de fusión. Booleano. Por defecto: Verdadero.  
  Los commit de fusión son aquellos que fusionan una rama y, en algunos casos, no se considera que reflejen una actividad de codificación

## Referencias

* https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name

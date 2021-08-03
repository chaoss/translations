# Cambios de código

Pregunta: ¿Cuántos cambios se realizaron en el código fuente durante un período específico?


## Descripción

Se trata de cambios en el código fuente durante un período determinado. Por «cambio» consideramos lo que los desarrolladores consideran un cambio atómico en su código. En otras palabras, un cambio es un cambio en el código fuente que generalmente se acepta y se fusiona como un todo, y si es necesario, también se revierte como un todo. Por ejemplo, en el caso de git, cada «cambio» corresponde a un «commit», o, para ser más precisos, un «cambio de código» corresponde a la parte de un commit que toca archivos considerados como código fuente.


## Objetivos

* Volumen de la actividad de codificación. Los cambios de código son un indicador de la actividad en un proyecto. Al contar los cambios de código en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad de codificación general en ese proyecto. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento de volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Cantidad. Número total de cambios durante el período.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período. Por defecto: para siempre. Período durante el cual se consideran los cambios.
* Criterios para el código fuente. Algoritmo. Por defecto: todos los archivos son código fuente. Si se centra en el código fuente, criterios para decidir si un archivo es parte del código fuente o no.


### Filtros

* Por actores (autor, committers). Requiere la fusión de actores (fusionar identificadores correspondientes al mismo autor).

* Por grupos de actores (empleador, género...). Requiere agrupación de actores, y probablemente, fusión de actores.

* Por [etiquetas](https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name) (utilizadas en el mensaje de los commits). Requiere una estructura para el mensaje de commits. Esta etiqueta se puede utilizar en un proyecto de código abierto para comunicar a todos los contribuyentes si el commit es, por ejemplo, una corrección de un error o una mejora de una función.

### Visualizaciones

* Cantidad por mes a lo largo del tiempo
* Cantidad por grupo a lo largo del tiempo

Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría cambios de código durante un período determinado (por ejemplo, un mes).


### Herramientas que proporcionan la métrica

* [GrimoireLab](https://chaoss.github.io/grimoirelab) proporciona esta métrica lista para usar.
  - Vea un ejemplo de en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/Git).
  - Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/panels/git/).
  - Añada una visualización de muestra a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Crear un nuevo gráfico de `Barras verticales`
    * Seleccione el índice `git`
    * Eje Y: Agregación `Cantidad única`, Campo `hash`, Etiqueta personalizada `# Commits`
    * Eje X: Agregación `Histograma de fechas`, Campo `grimoire_creation_date`, Intervalo `Automático`, Etiqueta personalizada `Hora`
  - Captura de pantalla de ejemplo: 
   
  ![Captura de pantalla de GrimoireLab de la métrica Code_Changes](images/code-changes_grimoirelab.png)

* [Augur](http://augur.osshealth.io/) proporciona esta métrica como [Cambios de código](http://augur.osshealth.io/api_docs/#api-Evolution-code_changes_repo/) y como [Líneas de cambios de código](http://augur.osshealth.io/api_docs/#api-Evolution-code_changes_lines_repo). Ambas métricas están disponibles en las formas métricas `repo` y `repo_group`. Puede encontrar más información al respecto en la documentación de [Augur](https://oss-augur.readthedocs.io/en/master/getting-started/create-a-metric/overview.html#metric-forms).

* [Gitdm](https://repo.or.cz/w/git-dm.git)


### Estrategias de recopilación de datos

**Descripción específica: Git**

Ver [implementación de referencia para git](https://github.com/chaoss/wg-evolution/blob/master/implementations/notebooks_df/code_changes_git.ipynb)

Parámetros obligatorios (para Git):

* Tipo de fecha. La fecha del autor o la fecha del committer. Por defecto: fecha del autor.  
  Para cada commit de git, se conservan dos fechas: cuándo se creó el commit y cuándo se efectuó el commit en el repositorio. Para decidir el período, se debe seleccionar uno de ellos.

* Incluir los commits de fusión. Booleano. Por defecto: Verdadero.  
  Los commit de fusión son aquellos que fusionan una rama y, en algunos casos, no se considera que reflejen una actividad de codificación.

* Incluir commits vacíos. Booleano. Por defecto: Verdadero.  
  Los commits vacíos son aquellos que no tocan archivos y, en algunos casos, no se considera que reflejen una actividad de codificación.

## Referencias

* https://www.odoo.com/documentation/13.0/reference/guidelines.html#tag-and-module-name

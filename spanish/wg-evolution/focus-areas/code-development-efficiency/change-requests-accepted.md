# Revisiones aceptadas

Pregunta: ¿Cuántas revisiones aceptadas hay en un cambio de código?

## Descripción

Las revisiones se definen como en [Revisiones](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews.md). Las revisiones aceptadas son aquellas que terminan con los cambios correspondientes finalmente fusionados en el código base del proyecto. Las revisiones aceptadas se pueden vincular a uno o más cambios en el código fuente, los correspondientes a los cambios propuestos y finalmente fusionados.

Por ejemplo, en GitHub cuando se acepta una solicitud de extracción, todos los commits incluidos en ella se combinan (tal vez se aplastan, tal vez se rebasan) en el repositorio de git correspondiente. Lo mismo puede decirse de las solicitudes de fusión de GitLab. En el caso de Gerrit, una revisión de código generalmente corresponde a un único commit.


## Objetivos

* Volumen de actividad de codificación.  
  Las revisiones de código aceptadas son un indicador de la actividad en un proyecto. Al contar las revisiones de código aceptadas en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad de codificación general en ese proyecto que provoca los cambios. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento de volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Cantidad. Número total de revisiones aceptadas durante el período.
* Proporción. Relación de revisiones aceptadas sobre el número total de revisiones durante ese período.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período durante el cual se consideran las revisiones aceptadas. Por defecto: para siempre.

* Criterios para el código fuente. Algoritmo. Por defecto: todos los archivos son de código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si un archivo es parte del código fuente o no.


### Filtros

* Por tipo de actor (remitente, revisor, fusión). Requiere la fusión de identidades correspondientes al mismo actor.
* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.


### Visualizaciones

* Cantidad por período de tiempo a lo largo del tiempo
* Proporción por período de tiempo a lo largo del tiempo

Estas se pueden agrupar por tipo de actor o por grupo de actores aplicando los filtros definidos anteriormente. Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría revisiones aceptadas para cambiar el código durante un período determinado (por ejemplo, un mes).


### Herramientas que proporcionan la métrica

* [Grimoirelab](https://chaoss.github.io/grimoirelab) proporciona esta métrica lista para usar para solicitudes de extracción de GitHub y también proporciona datos para generar visualizaciones similares para solicitudes de combinación de GitLab y conjuntos de cambios de Gerrit.
  - Vea un ejemplo de en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/a7b3fd70-ef16-11e8-9be6-c962f0cee9ae).
  - Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas basada en datos de Solicitudes de extracción de GitHub de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/panels/github-pullrequests/).
  - Añada una visualización de muestra para solicitudes de extracción de GitHub a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree una nueva visualización de `Timelion`.
    * Seleccione `Auto` como Intervalo.
    * Pegue la siguiente expresión de Timelion:
    ```
    .es(index=git, q="title:Merge* OR files:0", timefield=grimoire_creation_date).bars().color(#94c3af).label("Solicitudes de extracción fusionadas")
    ```
    * La expresión, paso a paso:
      * `.es()`: se usa para definir una consulta ElasticSearch.
        * `index=git`: utiliza el índice git.
        * `q="title:Merge* OR files:0"`: heurística para filtrar en fusiones.
        * `timefield=grimoire_creation_date`: el tiempo se basará en la fecha de creación del commit (ya que nuestra consulta busca commits de fusión, debería ser la fecha en la que se efectuó la fusión).
      * `.bars()`: dibujar barras en lugar de líneas.
      * `.color()` y `.label()`: algunas opciones de formato.
    * Si desea obtener también la tendencia, use esto en su lugar (es decir, repita la misma expresión dos veces y llame a `trend ()` la segunda vez):
    ```
    .es(index=git, q="title:Merge* OR files:0", timefield=grimoire_creation_date).bars().color(#94c3af).label("Solicitudes de extracción fusionadas"),
    .es(index=git, q="title:Merge* OR files:0", timefield=grimoire_creation_date).trend().color(#ffb745).label("Tendencia")
    ```
    * Tal ya como se ha mencionado [anteriormente para el caso de GitHub](#specific-description-github), a veces no es fácil identificar las fusiones. Como probablemente haya notado, en este ejemplo basamos nuestra expresión en el índice GrimoireLab Git. Además, podría aplicarse a cualquier otro entorno similar usando repositorios de Git, no solo a GitHub.
  - Captura de pantalla de ejemplo: ![Captura de pantalla de GrimoireLab de la métrica Revisiones aceptadas](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/reviews_accepted_GrimoireLab.png)


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, las revisiones aceptadas se definen como «solicitudes de extracción cuyos cambios se incluyen en el repositorio de git», siempre que proponga cambios en los archivos de código fuente.

Por desgracia, hay varias maneras de aceptar comentarios, y no todas ellas hacen que sea fácil identificar que fueron aceptados. La situación más fácil es cuando la solicitud de extracción se acepta y se fusiona (o se vuelve a basar, o se aplasta y se fusiona). En ese caso, la solicitud de extracción se puede identificar fácilmente como aceptada y los commits correspondientes se pueden encontrar mediante consultas a la API de GitHub.

Pero las revisiones también se pueden cerrar y los commits se pueden fusionar manualmente en el repositorio git. En este caso, los commits aún se pueden encontrar en el repositorio de git, ya que su hash es el mismo que se encuentra en la API de GitHub para aquellos en la solicitud de extracción.

En un escenario más difícil, las revisiones también pueden cerrarse y los commits rebasarse, o tal vez aplastarse y luego combinarse, manualmente. En estos casos, los hashes son diferentes, y solo se puede usar una coincidencia aproximada a través de fechas y autores, y/o una comparación de diferencias, para rastrear los commits en el repositorio de git.

Desde el punto de vista de saber si fueron aceptadas, el problema es que si se incluyen en el repositorio de git manualmente, la única forma de saber que se aceptó la solicitud de extracción es encontrar los commits correspondientes en el repositorio de git.

En algunos casos, los proyectos tienen políticas que obligan a mencionar los commits cuando se cierra la solicitud de extracción (como «cerrar aceptando los commits xxx y yyyy»), lo que puede ayudar a rastrear los commits en el repositorio de git.

Parámetros obligatorios (para GitHub):

* Heurística para detectar solicitudes de extracción aceptadas no aceptadas través de la interfaz web. Por defecto: Ninguno.

**Descripción específica: GitLab**

En el caso de GitLab, las revisiones aceptadas se definen como «solicitudes de fusión cuyos cambios se incluyen en el repositorio de git», siempre que proponga cambios en los archivos de código fuente.

Parámetros obligatorios (para GitLab):

* Heurística para detectar solicitudes de extracción aceptadas no aceptadas través de la interfaz web. Por defecto: Ninguno.

**Descripción específica: Gerrit**

En el caso de Gerrit, las revisiones aceptadas se definen como «conjuntos de cambios cuyos cambios se incluyen en el repositorio de git», siempre que propongan cambios en los archivos de código fuente.

Parámetros obligatorios (para Gerrit): Ninguno.



## Referencias
 

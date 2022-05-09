# Revisiones rechazadas

Pregunta: ¿Qué revisiones de cambios de código terminaron rechazando el cambio durante un período determinado?


## Descripción

Las revisiones se definen como en [Revisiones](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews.md). Las revisiones rechazadas son aquellas que finalmente se cierran sin que se fusione en la base de código del proyecto.

Por ejemplo, en GitHub, cuando una solicitud de extracción se cierra sin fusionar y los commits a los que se hace referencia no se pueden encontrar en el repositorio de git, se puede considerar rechazada (pero consulte la discusión detallada a continuación). Lo mismo puede decirse de las solicitudes de fusión de GitLab. En el caso de Gerrit, las revisiones de código pueden ser «abandonadas» formalmente, que es la forma de detectar revisiones rechazadas en este sistema.


## Objetivos

* Volumen de la actividad de codificación. Las revisiones de código rechazadas son un indicador de la actividad de un proyecto. Al contar las revisiones de código rechazadas en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad de codificación general en ese proyecto que no provoca los cambios. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento de volumen de actividad de codificación.



## Implementación

**Agregadores**:
* Cantidad. Número total de revisiones rechazadas durante el período.
* Proporción. Relación de revisiones rechazadas sobre el número total de revisiones durante ese período.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período durante el cual se consideran las revisiones rechazadas. Por defecto: para siempre.
* Criterios para el código fuente. Algoritmo. Por defecto: todos los archivos son de código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si un archivo es parte del código fuente o no.


### Filtros

* Por actores (remitente, revisor, fusión). Requiere la fusión de identidades correspondientes al mismo actor.
* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.


### Visualizaciones

* Cantidad por grupo a lo largo del tiempo
* Proporción por período a lo largo del tiempo

Estas podrían agruparse (por tipo de actor o por grupo de actores) aplicando los filtros, y podrían representarse como gráficos de barras, con el tiempo transcurrido en el eje X. Cada barra representaría las revisiones rechazadas durante un período determinado (por ejemplo, un mes).


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, las revisiones rechazadas se definen como «solicitudes de extracción que se han cerrado sin que sus cambios se incluyan en el repositorio de git», siempre que proponga cambios en los archivos de código fuente.

Vea la discusión en la descripción específica de GitHub en [Revisiones aceptadas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews_Accepted.md), ya que también se aplica aquí.

Parámetros obligatorios (para GitHub):

* Heurística para detectar solicitudes de extracción rechazadas, distinguiendo aquellos casos en los que la solicitud de extracción se cerró, pero los cambios se incluyeron en el repositorio de git manualmente. Por defecto: Ninguno.

**Descripción específica: GitLab**

En el caso de GitLab, las revisiones rechazadas se definen como «solicitudes de fusión que se han cerrado sin que los cambios se incluyan en el repositorio de git», siempre que proponga cambios en los archivos de código fuente.

Parámetros obligatorios (para GitLab):

* Heurística para detectar solicitudes de fusión rechazadas, distinguiendo aquellos casos en los que la solicitud de fusión se cerró, pero los cambios se incluyeron en el repositorio de git manualmente. Por defecto: Ninguno.

**Descripción específica: Gerrit**

En el caso de Gerrit, las revisiones rechazadas se definen como «conjuntos de cambios abandonados», siempre que propongan cambios en los archivos de código fuente.

Parámetros obligatorios (para Gerrit): Ninguno.

## Referencias


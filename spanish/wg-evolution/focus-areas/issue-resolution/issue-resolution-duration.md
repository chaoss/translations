# Duración de la resolución de la incidencia

Pregunta: ¿Cuánto tiempo se tarda en cerrar una incidencia?

## Descripción
Esta métrica es una indicación de cuánto tiempo permanece abierta una incidencia, en promedio, antes de que se cierre. Las incidencias se definen como en [Incidencias cerradas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md).

En el caso de las incidencias que se volvieron a abrir y cerrar, solo la última fecha de cierre es relevante para esta métrica.

## Objetivos
Esta métrica se puede utilizar para evaluar el esfuerzo y el tiempo necesarios para concluir y resolver discusiones. Esta métrica también puede proporcionar información sobre el nivel de capacidad de respuesta de un proyecto.

## Implementación

Para cada incidencia cerrada:
* Duración de la resolución de la incidencia = Marca de tiempo de la incidencia cerrada - Marca de tiempo de la incidencia abierta

**Agregadores:**
* Promedio. Cantidad de tiempo promedio (en días, de forma predeterminada) para que se cierre una incidencia en el repositorio.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período. Por defecto: para siempre.  
  Período durante el cual se consideran las incidencias.


### Filtros

* Por tiempo. Proporciona el tiempo medio de duración de la resolución de incidencias desde la fecha de inicio proporcionada hasta la fecha de finalización proporcionada.
  - Por tiempo abierta. Proporciona información sobre cuánto tiempo tardaron en resolverse las incidencias creadas desde la fecha de inicio proporcionada hasta la fecha de finalización proporcionada.
  - Por tiempo cerrada. Proporciona información sobre el tiempo que tardaron en resolverse las incidencias antiguas que se cerraron desde la fecha de inicio proporcionada hasta la fecha de finalización proporcionada.

* Por actores (remitente, comentarista, más cercano). Requiere la fusión de actores (fusión de identificadores correspondientes al mismo autor).

* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.



### Visualizaciones

* Promedio a lo largo del tiempo (por ejemplo, promedio de enero, promedio de febrero, promedio de marzo, etc.)
* Promedio de un período de tiempo determinado (por ejemplo, promedio de todo 2019 o promedio de enero a marzo)


### Herramientas que proporcionan la métrica

* [Augur](http://augur.osshealth.io/) proporciona esta métrica como [Duración de resolución de incidencia cerrada](http://augur.osshealth.io/api_docs/#api-Evolution-Closed_Issue_Resolution_Duration_Repo_). Estas métricas están disponibles en las formas métricas `repo` y `repo_group`. Puede encontrar más información al respecto en la [documentación de Augur](https://oss-augur.readthedocs.io/en/master/getting-started/create-a-metric/overview.html#metric-forms).


### Estrategias de recopilación de datos

Para obtener descripciones específicas de la recopilación de datos sobre incidencias cerradas, consulte la sección [correspondiente de Incidencias cerradas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md#data-collection-strategies).


## Referencias


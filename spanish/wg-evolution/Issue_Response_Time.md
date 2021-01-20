# Tiempo de respuesta a incidencias

Pregunta: ¿Cuánto tiempo pasa entre la apertura de una incidencia y la respuesta en el hilo de la incidencia por parte de otro contribuyente?

## Descripción
Esta métrica es una indicación de cuánto tiempo transcurre entre la apertura de una incidencia y la respuesta de otros contribuyentes.

Esta métrica es un caso específico de la [métrica Tiempo hasta la primera respuesta](https://github.com/chaoss/wg-common/blob/master/focus-areas/when/time-to-first-response.md) en el [Grupo de trabajo común](https://github.com/chaoss/wg-common).


## Objetivos
Obtenga información sobre la capacidad de respuesta de una comunidad de código abierto.

## Implementación

**Agregadores:**
* Promedio. Tiempo medio de respuesta en días.
* Media. Tiempo medio de respuesta en días.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período. Por defecto: para siempre.
*  Periodo durante el cual se contabilizan las respuestas.

### Filtros
* respuesta del rol en el proyecto (por ejemplo, respuesta del primer mantenedor)
* bot frente a humano (p. ej., filtrar «primeros mensajes de bienvenida al contribuyente» automatizados)
* abierto por rol en el proyecto (por ejemplo, capacidad de respuesta a nuevos contribuyentes frente a los que trabajan desde hace mucho tiempo)
* fecha en que se abrió la incidencia
* estado de la incidencia (por ejemplo, solo mirar las incidencias abiertas actualmente)

### Visualizaciones
![Visualización de ejemplo de GrimoireLab](images/issue_response_duration_grimoirelab.png)

### Herramientas que proporcionan la métrica
* GrimoireLab: [General para cualquier sistema de tickets](https://chaoss.github.io/grimoirelab-sigils/panels/efficiency-timing-overview/), [Incidencias de GitHub](https://chaoss.github.io/grimoirelab-sigils/panels/github-issues-efficiency/), [Incidencias de GitLab](https://chaoss.github.io/grimoirelab-sigils/panels/gitlab-issues-efficiency/)
* [Augur](http://augur.osshealth.io/api_docs/#api-Evolution-Issue_Response_Time_Repo_)

### Estrategias de recopilación de datos

Consulte la métrica [Nuevas incidencias](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md) para obtener una definición de «incidencias». Reste la marca de tiempo de apertura de la incidencia de la marca de tiempo de la primera respuesta. No cuente las respuestas si las creó el autor de la incidencia.

## Referencias

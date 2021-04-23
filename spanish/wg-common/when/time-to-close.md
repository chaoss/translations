# Tiempo hasta el cierre

Pregunta: ¿Cuánto tiempo pasa entre la creación y el cierre de una operación, como una incidencia, una revisión o un ticket de soporte?

## Descripción
El tiempo hasta el cierre es la cantidad total de tiempo que transcurre entre la creación y el cierre de una operación como una incidencia, una revisión o un ticket de soporte. La operación debe tener un estado abierto y cerrado, como suele ser el caso en los procesos de revisión de código, foros de preguntas y respuestas y sistemas de emisión de tickets.

Métrica relacionada: [Duración de la resolución de la incidencia](https://chaoss.community/metric-issue-resolution-duration/)

## Objetivos
1. Determinar en qué medida lo receptiva que sea una comunidad puede ayudar a que los esfuerzos sean inclusivos, atraigan y retengan contribuyentes nuevos y existentes.
2. Identificar las características de las operaciones que afectan a que una operación se cierre de forma rápida o lenta (por ejemplo, encontrar las mejores prácticas, áreas de mejora, evaluar la eficiencia).
3. Identificar sesgos para respuestas oportunas a diferentes miembros de la comunidad.
4. Detectar un cambio en la actividad de la comunidad (por ejemplo, para indicar un posible agotamiento del mantenedor, reducción en la diversidad de las contribuciones)

## Implementación

### Filtros

* Creador de la operación (p. ej., nuevo contribuyente vs. mantenedor)
* Primero cerrado, final cerrado
* etiquetas de incidencias (p. ej., error vs. nueva característica)

### Visualizaciones

![Tiempo medio para cerrar una incidencia de GrimoireLab](images/time-to-close_1.png)

### Herramientas que proporcionan la métrica

Implementación de Augur:
* [Duración del cierre de la incidencia](http://augur.osshealth.io/api_docs/#api-Evolution-Closed_Issue_Resolution_Duration(Repo))
* [Duración de la incidencia](http://augur.osshealth.io/api_docs/#api-Evolution-issue-duration-repo)
* [Tiempo de respuesta a la incidencia](http://augur.osshealth.io/api_docs/#api-Evolution-Issue_Response_Time(Repo))

Implementación de GrimoireLab:
* [Eficiencia de las solicitudes de extracción](https://chaoss.github.io/grimoirelab-sigils/panels/github-pullrequests-efficiency/)
* [Eficiencia de las incidencias](https://chaoss.github.io/grimoirelab-sigils/panels/github-issues-efficiency/)
* [Efficiency:TimingOverview](https://chaoss.github.io/grimoirelab-sigils/panels/efficiency-timing-overview/)

### Estrategias de recopilación de datos

El tiempo para cerrar la métrica puede ser contextual según la actividad y los objetivos del proyecto. Por ejemplo, el tiempo que se tarda en cerrar un informe de errores puede proporcionar información diferente que el tiempo que se tarda en cerrar una nueva solicitud de función. Las estrategias de recopilación de datos deben abordar diferentes objetivos del proyecto. Otras variables que pueden influir en estos procesos son:
* Sistemas de seguimiento de incidencias: el tipo de incidencia, como informe de error, plan (nomenclatura de OpenStack), historial del usuario, solicitud de función, épica y otros, puede influir en el tiempo que tarda en cerrarse este evento. Otras variables, como la prioridad o la gravedad, pueden ayudar a anticipar la rapidez con la que se cerrará este evento.
* Procesos de revisión de código: esto depende de la infraestructura de revisión de código, como Gerrit, GitHub o listas de correo (como en el Kernel de Linux) y puede diferir dependiendo de lo complicado que sea el proceso. Por ejemplo, los desarrolladores recién llegados o avanzados y experimentados procederán de diferentes maneras y requerirán de más o menos tiempo.
* Foro de preguntas y respuestas: depende de la calidad de la respuesta y de la opinión de la persona que hace la pregunta. Se marca una respuesta válida y el proceso se cierra una vez que la persona que pregunta ha encontrado con éxito una respuesta correcta a su pregunta.

## Referencias
* «Practice P.12: Respond to all submissions» de «Appendix to: Managing Episodic Volunteers in Free/Libre/Open Source Software Communities» de Ann Barcomb, Klaas-Jan Stol, Brian Fitzgerald y Dirk Riehle: https://opus4.kobv.de/opus4-fau/frontdoor/index/index/docId/13519  

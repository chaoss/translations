# Nuevas incidencias

Pregunta: ¿Cuántas incidencias nuevas se crean durante un período determinado?


## Descripción

Los proyectos discuten cómo están arreglando errores o añadiendo nuevas funciones, en tickets en el sistema de seguimiento de incidencias. Cada uno de estos tickets (incidencia) los abre (envía) una persona determinada y luego reciben comentarios y anotaciones de muchas otras personas.

Dependiendo del sistema de incidencias considerado, una incidencia puede pasar por varios estados (por ejemplo, «clasificada», «trabajando en ello», «solucionada», «no se solucionará«) o estar etiquetada con una o más etiquetas, o ser asignada a una o más personas. Pero en cualquier sistema de seguimiento de incidencias, una incidencia es por lo general una colección de comentarios y cambios de estado, tal vez con otras anotaciones. Las incidencias también pueden estar, en algunos sistemas, asociadas a hitos, ramas, épicas o historias. En algunos casos, algunas de estas también son incidencias en por sí mismas.

Por lo general, se pueden identificar al menos dos estados de «alto nivel»: abierta y cerrada. «Abierta» por lo general significa que la incidencia todavía no se ha resuelto, y «Cerrada» que la incidencia ya se resolvió, y no se hará ningún trabajo adicional. Sin embargo, lo que se puede utilizar para identificar una incidencia como «abierta» o «cerrada» depende hasta cierto punto del sistema de seguimiento de incidencias, y cómo lo utiliza un determinado proyecto. En proyectos reales, el filtrado de las incidencias que están directamente relacionadas con código fuente es difícil, ya que el sistema de seguimiento de incidencias se puede utilizar para muchos tipos de información, desde corregir errores y discutir la implementación de nuevas características, hasta la organización de un evento de proyecto o para hacer preguntas sobre cómo utilizar los resultados del proyecto.

En la mayoría de los rastreadores de incidencias, las incidencias se pueden volver a abrir después de cerrarlas. La reapertura de una incidencia se puede considerar como la apertura de una nueva incidencia (consulte los parámetros a continuación).

Por ejemplo, las «incidencias» se corresponden a «incidencias» en el caso de GitHub, GitLab o Jira, a «informes de errores» en el caso de Bugzilla, y a «incidencias» o «tickets» en otros sistemas.


## Objetivos

Volumen de incidencias discutidas en un proyecto. Las incidencias son un indicador de la actividad en un proyecto. Al contar las incidencias en las que se discute el código en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad general de discusión de incidencias en ese proyecto. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento del volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Cantidad. Número total de nuevas incidencias durante el período.
* Proporción. Relación de nuevas incidencias sobre el número total de incidencias durante ese período.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período durante el cual se consideran las incidencias. Por defecto: para siempre.

* Criterio para el código fuente. Algoritmo. Por defecto: todas las incidencias están relacionadas con el código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si una incidencia está relacionada con el código fuente o no.<br>

* Reabrir como nueva. Booleano. Por defecto: Falso.  
  Criterio para definir si las incidencias reabiertas se consideran nuevas.


### Filtros

* Por actores (remitente, comentarista, más cercano). Requiere la fusión de identidades correspondientes al mismo autor.
* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.


### Visualizaciones

* Cantidad por período de tiempo a lo largo del tiempo
* Proporción por período de tiempo a lo largo del tiempo

Estas se pueden agrupar aplicando los filtros definidos anteriormente. Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría propuestas para cambiar el código durante un período determinado (por ejemplo, un mes).


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, una incidencia se define como una «incidencia».

La fecha de la incidencia se puede definir (para considerarla en un período o no) como la fecha en que se abrió (envió) la incidencia.

**Descripción específica: GitLab**

En el caso de GitHub, una incidencia se define como una «incidencia».

La fecha de la incidencia se puede definir (para considerarla en un período o no) como la fecha en que se abrió (envió) la incidencia.

**Descripción específica: Jira**

En el caso de Jira, una incidencia se define como una «incidencia».

La fecha de la incidencia se puede definir (para considerarla en un período o no) como la fecha en que se abrió (envió) la incidencia.

**Descripción específica: Bugzilla**

En el caso de Bugzilla, una incidencia se define como un «informe de errores», siempre que esté relacionado con archivos de código fuente.

La fecha de la incidencia se puede definir (para considerarla en un período o no) como la fecha en que se abrió (envió) el informe de errores.

## Referencias


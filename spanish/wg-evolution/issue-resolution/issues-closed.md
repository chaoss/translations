# Incidencias cerradas

Pregunta: ¿Cuántas incidencias se cerraron durante un período determinado?


## Descripción

Las incidencias se definen como en [Incidencias nuevas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_New.md). Las incidencias cerradas son aquellas que cambiaron al estado cerrada durante un período determinado.

En algunos casos o en algunos proyectos, existen otros estados o etiquetas que podrían considerarse como «cerradas». Por ejemplo, en algunos proyectos usan el estado o la etiqueta «fixed» (corregida) para indicar que la incidencia está cerrada, incluso cuando necesita alguna acción para cerrarla formalmente.

En la mayoría de los rastreadores de incidencias, las incidencias cerradas se pueden volver a abrir después de que se hayan cerrado. La reapertura de una incidencia se puede considerar como la apertura de una nueva incidencia o la anulación del cierre anterior (consulte los parámetros a continuación).

Por ejemplo, en Incidencias de GitHub o Incidencias de GitLab, las incidencias cerradas son incidencias que se cerraron durante un período determinado.


## Objetivos

Volumen de incidencias que se tratan en un proyecto. Las incidencias cerradas son un indicador de la actividad en un proyecto. Al contar las incidencias cerradas relacionadas con el código en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad general de trabajo finalizado con incidencias en ese proyecto. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento del volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Cantidad. Número total de incidencias activas durante el período.
* Proporción. Relación de incidencias activas sobre el número total de incidencias durante ese período.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período durante el cual se consideran las incidencias. Por defecto: para siempre.

* Criterios para el código fuente. Algoritmo. Por defecto: todas las incidencias están relacionadas con el código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si una incidencia está relacionada con el código fuente o no. Todas las incidencias se pueden incluir en la métrica modificando el valor predeterminado.

* Reabrir como nueva. Booleano, que define si las incidencias reabiertas se consideran como incidencias nuevas. Si es falso, significa que el evento de cierre anterior a un evento de reapertura debe considerarse vacío. Nota: si este parámetro es falso, el número de incidencias cerradas para cualquier período podría cambiar en el futuro, si algunas de ellas se vuelven a abrir.

* Criterios para cerrada. Algoritmo. Por defecto: tener un evento de cierre durante el período de interés.


### Filtros

* Por actores (remitente, comentarista, más cercano). Requiere la fusión de identidades correspondientes al mismo autor.

* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.


### Visualizaciones

* Cantidad por período de tiempo a lo largo del tiempo
* Proporción por período de tiempo a lo largo del tiempo

Estas se pueden agrupar aplicando los filtros definidos anteriormente. Estas podrían representarse como gráficos de barras, con el tiempo en el eje X.


### Herramientas que proporcionan la métrica

* [GrimoireLab](https://chaoss.github.io/grimoirelab) proporciona datos para calcular esta métrica para incidencias de GitHub, incidencias de GitLab, Jira, Bugzilla y Redmine. Los paneles de control actuales muestran información basada en la fecha de creación, lo que significa que muestran el estado actual de las incidencias que se crearon durante un período de tiempo (por ejemplo, [panel de control de incidencias de GitHub](https://chaoss.github.io/grimoirelab-sigils/panels/github-issues/), puede [verlo en acción](https://chaoss.biterg.io/app/kibana#/dashboard/GitHub-Issues)). Sin embargo, es fácil construir una visualización que muestre incidencias basadas en la fecha de cierre siguiendo los siguientes pasos:
  - Añada una visualización de muestra a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree un nuevo gráfico de `Barras verticales`.
    * Seleccione el índice `github_issues`.
    * Filtro: `pull_request` es `falso`.
    * Filtro: `state` es `cerrada`.
    * Métricas del eje Y: Agregación `Cantidad`, Etiqueta personalizada `# Incidencias cerradas`.
    * Cubos del eje X: Agregación `Histograma de fechas`, Campo `cerrado_a_las`, Intervalo `Semanal` (o cualquier intervalo que se ajuste a sus necesidades, dependiendo del rango de tiempo completo que desee visualizar en el gráfico), Etiqueta personalizada `Hora`.
  - Captura de pantalla de ejemplo: 
     
  ![GrimoireLab screenshot of metric issues_closed](images/issues-closed_grimoirelab.png).


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, las incidencias cerradas se definen como «incidencias que están cerradas».

**Descripción específica: GitLab**

En el caso de GitLab, las incidencias activas se definen como «incidencias que están cerradas».

**Descripción específica: Jira**

En el caso de Jira, las incidencias activas se definen como «incidencias que cambian al estado cerrada».

**Descripción específica: Bugzilla**

En el caso de Bugzilla, las incidencias activas se definen como «informes de errores que cambian al estado cerrado».

## Referencias


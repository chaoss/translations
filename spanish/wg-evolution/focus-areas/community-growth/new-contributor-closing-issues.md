# Nuevos contribuyentes que cierran incidencias

Pregunta: ¿Cuántos contribuyentes están cerrando incidencias por primera vez en un proyecto determinado?

## Descripción
Esta métrica es una indicación del volumen de contribuyentes que están cerrando incidencias por primera vez dentro de un proyecto determinado. Cuando un contribuyente cierra una incidencia por primera vez, es un indicio de «adhesión» del individuo dentro de ese proyecto, especialmente para los contribuyentes que no son también committers.

## Objetivos
Conocer cómo se mueven los contribuyentes a través del [embudo del contribuyente](https://mikemcquaid.com/2018/08/14/the-open-source-contributor-funnel-why-people-dont-contribute-to-your-open-source-project/) identificando «cerrar incidencias» como un hito en el recorrido del contribuyente.

## Implementación

**Agregadores:**
* Cantidad. Número total de contribuyentes que cierran incidencias en este proyecto por primera vez durante un período de tiempo determinado.
* Porcentaje. Proporción de contribuyentes que cierran incidencias en este proyecto *por primera vez* durante un período de tiempo determinado, calculado en relación con *todos* los contribuyentes que han cerrado incidencias en este proyecto durante el mismo período de tiempo.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período durante el cual se cuentan los nuevos cierres de incidencias. Por defecto: para siempre (es decir, toda la vida útil del proyecto observable)

### Filtros
* Excluir las incidencias reabiertas (opcionalmente, filtrar si se reabre en menos de 1 hora)

### Visualizaciones
* Tabla con los nombres de los contribuyentes que cerraron una incidencia por primera vez y cuándo fue.
* Línea de tiempo que muestra el tiempo en el eje x y el valor métrico agregado en el eje y para períodos de tiempo consecutivos fijos (por ejemplo, mensualmente). Esta visualización permite mostrar cómo evoluciona la métrica en el tiempo para el proyecto considerado.

### Estrategias de recopilación de datos
Según las definiciones de [Incidencias cerradas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md) y [Contribuyentes](https://github.com/chaoss/wg-common/blob/master/focus-areas/who/contributors.md), enriquezca a los contribuyentes con la fecha de la primera vez que cierran una incidencia.

## Referencias

* [Embudo de contribuyentes por Mike McQuaid](https://mikemcquaid.com/2018/08/14/the-open-source-contributor-funnel-why-people-dont-contribute-to-your-open-source-project/)

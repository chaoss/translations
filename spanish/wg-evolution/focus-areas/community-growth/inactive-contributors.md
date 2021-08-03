# Contribuyentes inactivos

Pregunta: ¿Cuántos Contribuyentes han estado inactivos durante un período de tiempo específico?


## Descripción
Una métrica que muestra cuántos contribuyentes han dejado de contribuir durante un período de tiempo específico. El período de tiempo necesario para que un contribuyente se cuente como inactivo se puede decidir mediante una variable y esta métrica mostrará el número de contribuyentes que se han etiquetado como inactivos durante un período de tiempo determinado.

## Objetivos
El objetivo es determinar cuántas personas han dejado de contribuir activamente. Esto podría ser útil para que los administradores de la comunidad determinen si los miembros clave están perdiendo interés o se están tomando un descanso.

## Implementación
La métrica tomará dos variables: un período de tiempo y un intervalo. El período de tiempo será el período durante el cual se mostrará el número de miembros inactivos. Por ejemplo, si período de tiempo = año, se mostrará el número de contribuyentes que han estado inactivos cada año. El intervalo determinará cuánto tiempo tarda un contribuyente en ser etiquetado como inactivo. Si un contribuyente no ha realizado una contribución durante un período de tiempo superior al intervalo, se contará como inactivo.

La métrica funcionará de la siguiente manera:
1. se obtiene una lista de todos los contribuyentes;
2. se comprueba la fecha de la última contribución;
3. si la fecha de la última contribución es anterior al límite, se les añade al recuento de inactividad del período en el que contribuyeron por última vez;
4. se crea una lista de contribuyentes inactivos.

**Agregadores:**
- inactivos: número de contribuyentes inactivos

### Filtros
- Contribuciones mínimas requeridas para ser considerado activo
- Período de tiempo para determinar la inactividad
- Fecha de inicio/Fecha de finalización
- Período del gráfico

### Estrategias de recopilación de datos
La lista de contribuyentes se puede recopilar utilizando la métrica de contribuyentes existentes. Para determinar la fecha de la última contribución, es posible que se necesite un nuevo código.

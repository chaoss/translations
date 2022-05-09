# Duración de las revisiones

Pregunta: ¿Cuál es el período de tiempo entre el momento en que comienza una revisión de código y el momento en que se acepta?


## Descripción

Las revisiones se definen como en [Revisiones](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews.md). Las revisiones aceptadas se definen en [Revisiones aceptadas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews_Accepted.md).

La duración de la revisión es la duración del período desde que comenzó la revisión del código hasta el momento en que finalizó (al ser aceptada y fusionarse en la base del código). Esto solo se aplica a las revisiones aceptadas.

Por ejemplo, en GitLab, una solicitud de fusión comienza cuando un desarrollador carga una propuesta para un cambio en el código y abre una solicitud de fusión. Finaliza cuando finalmente se acepta la propuesta y se fusiona en el código base, cerrando la solicitud de fusión.

En caso de que haya observaciones u otros eventos después de que el código se haya fusionado, no se tiene en cuenta para medir la duración de la de la revisión de código.


## Objetivos

* Duración de los procesos de aceptación de contribuciones. La duración de la revisión de las revisiones aceptadas es uno de los indicadores que muestran cuánto tiempo tarda un proyecto en aceptar una contribución de código. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento de volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Media. Media (percentil del 50%) de la duración de la revisión para las revisiones aceptadas en el período considerado.

**Parámetros:**
* Período de tiempo. Fecha de inicio y finalización del período. Por defecto: para siempre.  
  Período durante el cual se consideran las revisiones aceptadas. Se considera que una revisión aceptada está en el período si su evento de creación está en el período.

* Criterios para el código fuente. Algoritmo. Por defecto: todos los archivos son de código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si un archivo es parte del código fuente o no.

### Filtros

* Por actores (remitente, revisor, fusión). Requiere la fusión de actores (fusionar identificadores correspondientes al mismo autor).
* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.


### Visualizaciones

* Media por mes a lo largo del tiempo
* Media por grupo a lo largo del tiempo

Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría revisiones aceptadas para cambiar el código durante un período determinado (por ejemplo, un mes).

* Distribución de duraciones para un período determinado

Estas podrían representarse con las curvas de distribución estadística habitual, o con gráficos de barras, con intervalos de duración en el eje X y el número de revisiones en el eje Y.


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, la duración se considera para las solicitudes de extracción que se aceptan y se fusionan en la base de código. Para una solicitud de extracción individual, la duración comienza cuando se abre y finaliza cuando los commits que incluye se fusionan en la base del código.

Parámetros obligatorios (para GitHub): Ninguno.

**Descripción específica: GitLab**

En el caso de GitLab, la duración se considera para las solicitudes de fusión que se aceptan y se fusionan en la base de código. Para una solicitud de fusión individual, la duración comienza cuando se abre y finaliza cuando los commits que incluye se fusionan en la base del código.

Parámetros obligatorios (para GitLab): Ninguno.

**Descripción específica: Gerrit**

En el caso de Gerrit, la duración se considera para las revisiones de código que se aceptan y se fusionan en la base del código. Para una revisión de código individual, la duración comienza cuando se abre, y finaliza cuando los commits que incluye se fusionan en la base del código.

Parámetros obligatorios (para Gerrit): Ninguno.

## Referencias


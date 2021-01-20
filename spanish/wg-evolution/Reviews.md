# Revisiones

Pregunta: ¿Qué nuevas solicitudes de revisión de cambios en el código fuente se produjeron durante un período determinado?

## Descripción
Cuando un proyecto utiliza los procesos de revisión de código, los cambios no son directamente enviados a la base de código, sino que se proponen primero para discutirlos como «propuestas de cambio al código fuente». Cada una de estas propuestas está destinada a ser revisada por otros desarrolladores, quienes pueden sugerir mejoras que llevarán a los proponentes originales a enviar nuevas versiones de sus propuestas, hasta que las revisiones sean positivas y el código sea aceptado, o hasta que se decida que la propuesta es rechazada.

Por ejemplo, las «revisiones» se corresponden a «solicitudes de extracción» en el caso de GitHub, a «solicitudes de fusión» en el caso de GitLab, y a «revisiones de código» o en algunos contextos «conjuntos de cambios» en el caso de Gerrit.


## Objetivos
* Volumen de cambios propuestos a un proyecto. Las revisiones son un indicador de la actividad en un proyecto. Al contar las revisiones de código en el conjunto de repositorios correspondientes a un proyecto, puede tener una idea de la actividad de revisión de cambios en ese proyecto. Por supuesto, esta métrica no es la única que se debe utilizar para realizar un seguimiento de volumen de actividad de codificación.


## Implementación

**Agregadores:**
* Cantidad. Número total de revisiones durante el período.

**Parámetros:**

* Período de tiempo. Fecha de inicio y finalización del período. Por defecto: para siempre.  
  Período durante el cual se consideran las revisiones.

* Criterios para el código fuente. Algoritmo. Por defecto: todos los archivos son de código fuente.  
  Si nos centramos en el código fuente, necesitamos un criterio para decidir si un archivo es parte del código fuente o no.


### Filtros

* Por actores (remitente, revisor, fusión). Requiere la fusión de actores (fusionar identificadores correspondientes al mismo autor).
* Por grupos de actores (empleador, género... para cada uno de los actores). Requiere agrupación de actores, y probablemente, fusión de actores.
* Estado (abierta, cerrada)


### Visualizaciones

* Cantidad por mes a lo largo del tiempo
* Cantidad por grupo a lo largo del tiempo

Estas podrían representarse como gráficos de barras, con el tiempo en el eje X. Cada barra representaría revisiones para cambiar el código durante un período determinado (por ejemplo, un mes).



### Herramientas que proporcionan la métrica

* [Grimoirelab](https://chaoss.github.io/grimoirelab) proporciona esta métrica lista para usar para solicitudes de extracción de GitHub, solicitudes de combinación de GitLab y conjuntos de cambios de Gerrit.
  - Vea un ejemplo de en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/GitHub-Pull-Requests).
  - Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas basada en datos de Solicitudes de extracción de GitHub de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/panels/github-pullrequests/).
  - Añada una visualización de muestra para solicitudes de extracción de GitHub a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree un nuevo gráfico de `Barras verticales`.
    * Seleccione el índice `github_issues`.
    * Filtro: `pull_request` es `verdadero`.
    * Métricas del eje Y: Agregación `Cantidad`, Etiqueta personalizada `# Solicitudes de extracción`.
    * Eje X: Agregación `Histograma de fechas`, Campo `grimoire_creation_date`, Intervalo `Automático`, Etiqueta personalizada `Hora`.
    * Series divididas en cubos: Sub Agregación `Términos`, Campo `state`, Ordenar por `métrica: # Solicitudes de extracción`, Orden `Descendente`, Tamaño `1000`, Etiqueta personalizada `Estado`. Tenga en cuenta que esta visualización se basa en la fecha de creación de las solicitudes de extracción, por lo que los elementos se cuentan en la fecha en la que se crearon y su estado, como se establece aquí, sería su estado actual en el momento de visualizar los datos, por ejemplo, `n` de solicitudes de extracción creadas en un rango de tiempo determinado que están actualmente `abiertas` o `cerradas`.
  - Captura de pantalla de ejemplo: ![Captura de pantalla de GrimoireLab de la métrica Revisiones](https://github.com/chaoss/wg-evolution/blob/master/metrics/images/reviews-GrimoireLab.png)


### Estrategias de recopilación de datos

**Descripción específica: GitHub**

En el caso de GitHub, una revisión se define como una «solicitud de extracción», siempre que proponga cambios en los archivos de código fuente.

La fecha de la revisión se puede definir (para considerarla en un período o no) como la fecha en que se envió la solicitud de extracción.

**Descripción específica: GitLab**

En el caso de GitLab, una revisión se define como una «solicitud de fusión», siempre que proponga cambios en los archivos de código fuente.

La fecha de la revisión se puede definir (para considerarla en un período o no) como la fecha en que se envió la solicitud de fusión.

**Descripción específica: Gerrit**

En el caso de Gerrit, una revisión se define como una «revisión de código», o en algunos contextos, un «conjunto de cambios», siempre que proponga cambios en los archivos de código fuente.

La fecha de la revisión se puede definir (para considerarla en un período o no) como la fecha en la que se inició la revisión del código enviando un conjunto de parches para su revisión.

## Referencias

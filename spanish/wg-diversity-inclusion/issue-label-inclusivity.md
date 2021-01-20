# Inclusividad del etiquetado de incidencias
Pregunta: ¿Cómo de bien están etiquetadas las incidencias del proyecto para invitar a nuevos contribuyentes, contribuyentes cualificados, contribuyentes de aspectos no relacionados con el código y otros tipos de contribuyentes?


## Descripción
La inclusividad de las etiquetas de incidencias ayuda a medir la asequibilidad de las incidencias para diferentes contribuyentes en diferentes niveles de familiaridad (p. ej., recién llegado, contribuyente ocasional y contribuyentes principales), con diferentes habilidades (p. ej., lenguajes, frameworks, API, documentación, frontend y backend) y con diferentes objetivos (por ejemplo, contribuciones de código y no código).

## Objetivos

*__Apta para recién llegados__*: Las incidencias incluyen incidencias debidamente etiquetadas (p. ej., «buena primera incidencia», «apta para recién llegados») para que un nuevo contribuyente comience

*__Disponibilidad de mentor__*: Las incidencias identifican a un mentor que puede brindar orientación y ayudar con el proceso de revisión de una incidencia en particular (por ejemplo, etiqueta «Mentor disponible»)

*__Diversidad de la lista de incidencias__*: Las incidencias proporcionan una lista diversa de etiquetas que pertenecen a diferentes tipos de contribuciones (código y/o no código) (por ejemplo, etiqueta «Documentación»)

*__Título y descripción utilizables__*: Los títulos y descripciones de las incidencias siguen los objetivos de la métrica de Usabilidad de la documentación

*__Uso consistente de las etiquetas__*: Las incidencias utilizan una lista seleccionada de etiquetas con distintos colores de forma consistente. Por ejemplo, familias de etiquetas con un color distinto para cada una:

- Tipo de incidencia: «Característica» vs «Error» vs «Documentación»...
- Habilidades para las incidencias: las habilidades necesarias para resolver la incidencia (por ejemplo, js, html, css)
- Nivel de familiaridad de la incidencia: menciona el nivel más bajo de familiaridad necesario («buena para principiantes» o «contribuyente ocasional» o «contribuyente principal»...)

## Implementación

#### Filtro

- Tipo de etiqueta
- Tipo de repositorio
- Antigüedad de la incidencia abierta
- Número de incidencias abiertas
- Fecha en que se abrió la incidencia
- Problemas relacionados con el código frente a problemas relacionados con la documentación

#### Visualización
![ejemplo nº 1 del laboratorio de girimoire](images/grimoire-lab-viz-example1.png) ![ejemplo nº 2 del laboratorio de girimoire](images/grimoire-lab-viz-example2.png)


![etiquetas de ejemplo del proyecto kubernetes](images/kubernetes-labels-example.png) De: https://github.com/kubernetes/kubernetes/labels

#### Herramientas que proporcionan la métrica:
- GrimoireLab
- Augur

### Estrategias de recopilación de datos

- Identifique la lista publicada de etiquetas de incidencias utilizadas para cada proyecto
   - *Etiquetas generales*:
      - Presencia de etiquetas para identificar necesidades generales de «Característica», «Error» y «Documentación», una etiqueta «Interfaz» y una etiqueta «Back End» en la lista de etiquetas del proyecto y en la lista de incidencias (etiquetas en uso)
   - *Etiquetas inclusivas*:
     - Las Aptas para recién llegados buscan (*recién llegados*, *primera*) en la lista de etiquetas del proyecto y en la lista de incidencias (etiquetas en uso)
     - Las Aptas para mentores buscan (*mentor*) en la lista de etiquetas del proyecto y en la lista de incidencias (etiquetas en uso)

  - *Etiquetas de habilidad*:
     - Presencia de etiquetas para identificar las habilidades necesarias (por ejemplo, Java, Python, HTML, aprendizaje automático) en la lista de etiquetas del proyecto y en la lista de incidencias (etiquetas en uso)

- Observe la frecuencia con la que se utiliza cada etiqueta en las incidencias de un proyecto

## Referencias
- [Satélite de GitHub](https://githubsatellite.com/)

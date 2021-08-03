# Inversión laboral

Pregunta: ¿Cuál fue el coste de una organización para sus empleados para crear las contribuciones contadas (por ejemplo, commits, incidencias y solicitudes de extracción)?

## Descripción

Los proyectos de código abierto a menudo son respaldados por las organizaciones a través de inversiones laborales. Esta métrica hace un seguimiento de la inversión monetaria de las organizaciones (como se evidencia en los costes laborales) en proyectos individuales.

## Objetivos

A medida que el compromiso organizacional con los proyectos de código abierto se vuelve cada vez más importante, es fundamental que las organizaciones comprendan claramente su inversión laboral. El objetivo de esta métrica es mejorar la transparencia en los costes laborales para las organizaciones involucradas con proyectos de código abierto. Esta métrica le brinda al gerente de la Oficina de programas de código abierto (OSPO) una forma de comparar los costes laborales contribuidos en una cartera de proyectos. Por ejemplo, la métrica de Inversión laboral se puede utilizar para priorizar inversiones o determinar el retorno de la inversión, como por ejemplo:

  * Inversión laboral como medio para evaluar las prioridades de la OSPO y justificar presupuestos
  * Inversión laboral como una forma de explicar la prioridad de la gestión de productos/programas
  * Inversión laboral como argumento del valor de seguir invirtiendo en OSPO
  * Inversión laboral para informar y comparar los costes laborales del trabajo contribuido frente al trabajo interno
  * Inversión laboral para comparar la efectividad de los proyectos en una cartera de proyectos

## Implementación

Las métricas base incluyen:

- número de contribuciones
- número de contribuciones desglosadas por tipo de contribuyente (interno / externo)
- número de contribuciones desglosadas por tipos de contribución (p. ej., commits, incidencias, solicitudes de extracción)

Los parámetros incluyen:

- tarifa de trabajo por hora
- promedio de horas laborales para crear la contribución (por tipo de contribución)

Inversión laboral = Para cada tipo de contribución, suma (Número de contribuciones * Promedio de horas laborales para crear la contribución * Tarifa media por hora)

### Filtros

* contribuyentes internos vs externos
* etiquetas de incidencias
* fuentes del proyecto (por ejemplo, internas, repositorios de código abierto, repositorios de código abierto de la competencia)

### Visualizaciones

![csv](images/labor-investment_csv.png)

Nuestra primera visualización de métricas parametrizadas se basa en exportaciones CSV que pueden estar disponibles en Augur. Las hojas de cálculo se utilizan para parámetros métricos y fórmulas de cálculo.  Es posible que en implementaciones futuras se añadan funciones para la manipulación de parámetros directamente en la aplicación web.


## Referencias

- [Iniciar una Oficina de programas de código abierto](https://www.slideshare.net/caniszczyk/starting-an-open-source-program-office-ospo)
- [Crear una Oficina de programas de código abierto](https://events19.linuxfoundation.org/wp-content/uploads/2018/07/OSLS_2019-untold-story-of-OSPO.pdf)
- [El código abierto en la empresa](https://d1.awsstatic.com/Open%20Source/enterprise-oss-book.pdf)

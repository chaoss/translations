# Velocidad del proyecto

Pregunta: ¿Cuál es la velocidad de desarrollo de una organización?

## Descripción

La velocidad del proyecto es el número de incidencias, el número de solicitudes de extracción, el volumen de commits y el número de contribuyentes como indicador de «innovación».

## Objetivos

Ofrece a un administrador de la Oficina de programas de código abierto (OSPO) una forma de comparar la velocidad del proyecto en una cartera de proyectos.

El gerente de la OSPO puede usar la métrica de Velocidad del proyecto para:

- Informar sobre la velocidad de los proyectos de código abierto en comparación con los proyectos internos
- Comparar la velocidad del proyecto en una cartera de proyectos
- Identificar qué proyectos crecen más allá de los contribuyentes internos (cuando se filtran los contribuyentes internos en comparación con los externos)
- Identificar áreas prometedoras en las que participar
- Resaltar las áreas que probablemente serán plataformas exitosas en los próximos años

[Ver ejemplo](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects)

## Implementación

Las métricas base incluyen:

- [incidencias cerradas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Issues_Closed.md)
- [número de reseñas](https://github.com/chaoss/wg-evolution/blob/master/metrics/Reviews.md)
- [nº de cambios de código](https://github.com/chaoss/wg-evolution/blob/master/metrics/Code_Changes.md)
- [nº de committers](https://github.com/chaoss/wg-risk/blob/master/metrics/Committers.md)

### Filtros

* Contribuyentes internos vs externos
* Fuentes del proyecto (por ejemplo, repositorios internos, repositorios de código abierto y repositorios de código abierto de la competencia)
* Tiempo

### Visualizaciones

* Eje X: escala logarítmica para cambios de código
* Eje Y: escala logarítmica de la Suma del número de incidencias y el Número de revisiones
* Tamaño de punto: Committers
* Los puntos son proyectos

![cncf](images/project-velocity_visualization.png)

[De CNCF](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects/)

### Herramientas que proporcionan la métrica

* CNCF: https://github.com/cncf/velocity

## Referencias

- [¿Puede la innovación de código abierto funcionar en la empresa?](https://www.threefivetwo.com/blog/can-open-source-innovation-work-in-the-enterprise)
- [Innovación de código abierto para una cultura de alto rendimiento](https://www.nearform.com/blog/want-a-high-performing-culture-make-way-for-open-innovation)
- [Código abierto para la empresa digital](https://www.cio.com/article/3213146/open-source-is-powering-the-digital-enterprise.html)
- [Proyectos de código abierto de mayor velocidad](https://www.cncf.io/blog/2017/06/05/30-highest-velocity-open-source-projects)

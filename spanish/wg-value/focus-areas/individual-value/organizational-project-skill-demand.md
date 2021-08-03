# Demanda de habilidades de proyectos organizacionales

Pregunta: ¿Cuántas organizaciones están usando este proyecto y podrían contratarme si me vuelvo competente?


## Descripción

Las organizaciones se involucran con proyectos de código abierto a través del uso y las dependencias. Esta métrica tiene como objetivo determinar la demanda a posteriori de las habilidades relacionadas con un proyecto de código abierto. Esta métrica atiende a las organizaciones que implementan un proyecto como parte de una infraestructura de TI, otros proyectos de código abierto con dependencias declaradas y referencias al proyecto a través de las redes sociales, menciones en conferencias, publicaciones en blogs y actividades similares.


## Objetivos

Como desarrollador, me gustaría invertir mis habilidades y tiempo en un proyecto que tenga posibilidades de conseguirme un trabajo bien remunerado en el futuro. Las personas pueden usar la métrica Impacto organizacional a posteriori de un software de proyecto para descubrir qué proyectos utilizan las organizaciones y, por lo tanto, pueden buscar oportunidades de trabajo que probablemente requieran servicios de soporte de TI.


## Implementación

Las métricas base incluyen:
- Número de organizaciones que crearon incidencias para un proyecto
- Número de organizaciones que crearon solicitudes de extracción para un proyecto
- Número de organizaciones que bloguean o tuitean sobre un proyecto
- Número de organizaciones que mencionan un proyecto en las solicitudes de contratación abiertas
- Número de organizaciones que están representadas en reuniones sobre este proyecto
- Número de otros proyectos que dependen de un proyecto
- Número de libros sobre un proyecto
- Tendencias de búsqueda de Google para un proyecto


### Visualizaciones

La siguiente visualización demuestra el número de proyectos a posteriori dependientes del proyecto en cuestión. Si bien esta visualización no captura de la totalidad de la métrica Impacto organizacional a posteriori de un software de proyecto, proporciona una representación visual de una parte.

![imagen de papel](images/organizational-project-skill-demand_paper.png)

Otras visualizaciones podrían incluir tendencias de búsqueda de Google (reactiva vs. angular vs. Vue.js)

![Tendencias de Google](images/organizational-project-skill-demand_google-trends.png)

ThoughtWorks publica una serie llamada «Tech Radar» que muestra la popularidad de las tecnologías

![TechRadar](images/organizational-project-skill-demand_tech-radar.png)

Tech Radar le permite profundizar en los proyectos para ver cómo ha cambiado la evaluación con el tiempo.

![Evaluación](images/organizational-project-skill-demand_tech-react.png)

StackOverview publica una encuesta anual para desarrolladores

![StackOverflow](images/organizational-project-skill-demand_stack-overflow.png)


### Herramientas que proporcionan la métrica

* Tendencias de Google: para mostrar interés de búsqueda a lo largo del tiempo
* TechRadar de ThoughtWorks: evaluaciones de proyectos de una consultoría tecnológica
* Encuesta para desarrolladores de StackOverflow: clasificaciones anuales de proyectos
* Augur; Hay ejemplos disponibles para varios repositorios:
  - [Rails](http://augur.osshealth.io/repo/Rails%20(wg-value)/rails/overview)
  - [Zephyr](http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/overview)
  - [CloudStack](http://augur.osshealth.io/repo/Apache%20(wg-value)/cloudstack/overview)

## Referencias

- [Patrocinadores de código abierto](https://opensource.org/sponsors)
- [Patrocinadores fiscales y código abierto](https://opensource.com/article/19/1/fiscal-sponsors-open-source)
- [Grandes patrocinadores corporativos de código abierto](https://www.networkworld.com/article/2867020/big-names-like-google-dominate-open-source-funding.html)
- [API de Tendencias de Google](https://www.npmjs.com/package/google-trends-api)
- [Medición del impacto del software de código abierto](https://aisel.aisnet.org/cgi/viewcontent.cgi?article=1496&context=amcis2018)
- [Tech Radar de ThoughtWorks](https://www.thoughtworks.com/radar)
- [Encuesta para desarrolladores de Stack Overflow](https://insights.stackoverflow.com/survey/2019#technology)

# Licencias aprobadas por OSI

Pregunta: ¿Qué porcentaje de las licencias de un proyecto son licencias de código abierto aprobadas por OSI?

## Descripción

Esta métrica proporciona transparencia sobre las licencias de código abierto utilizadas dentro de un proyecto. La razón de la transparencia necesaria es que se están propagando varias licencias que, de hecho, no son aptas para el código abierto. Es posible que los proyectos de código abierto no quieran incluir ninguna licencia que no esté aprobada por OSI.

Según OSI: «Las licencias de código abierto son licencias que cumplen con la definición de código abierto; en resumen, permiten que el software se use, modifique y comparta libremente. Para ser aprobada por Open Source Initiative (también conocida como OSI), una licencia debe pasar por el proceso de revisión de licencias de Open Source Initiative».

## Objetivos

Identificar si un proyecto tiene licencias presentes que no se ajustan a la definición de código abierto. Esta transparencia ayuda a los proyectos a tomar decisiones conscientes sobre si incluir o no licencias que no están aprobadas por OSI.

## Implementación

Las licencias aprobadas por OSI se pueden encontrar en el archivo [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) proporcionado por SPDX.

### Visualizaciones

![OSI](images/osi-approved-licenses_visualization.png)

### Herramientas que proporcionan la métrica

Augur proporciona esta métrica en la página Riesgo de un proyecto.

Ejemplo: http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk

### Estrategias de recopilación de datos

Extraiga la lista de licencias de una base de código, igual que en la métrica Cobertura de licencia. Compare la lista de licencias con el archivo [Licenses.json](https://raw.githubusercontent.com/spdx/license-list-data/master/json/licenses.json) y anote cuántas licencias están aprobadas por OSI. Calcule el porcentaje de archivos en la lista de licencias OSI.

## Recursos

* [Página de licencias de OSI](https://opensource.org/licenses)
* [Lista de licencias de SPDX](https://spdx.org/licenses/)



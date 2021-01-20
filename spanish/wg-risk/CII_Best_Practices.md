# Insignia de Mejores Prácticas de la Iniciativa de Infraestructura Central

Pregunta: ¿Cuál es el estado actual de las mejores prácticas de la CII para el proyecto?

## Descripción

De acuerdo con la [página de la Insignia de Mejores Prácticas de la CII](https://bestpractices.coreinfrastructure.org/en): La insignia de Mejores Prácticas de la Iniciativa de Infraestructura Central (CII) de la Fundación Linux es una forma en que los proyectos de código abierto demuestran que siguen las mejores prácticas. Los proyectos pueden autocertificarse voluntariamente, sin coste, utilizando esta aplicación web para explicar cómo siguen cada una de las mejores prácticas. Los proyectos reciben la insignia de aprobación si cumplen con todos los criterios requeridos.

## Objetivos

De acuerdo con la [página de la Insignia de Mejores Prácticas de la CII](https://bestpractices.coreinfrastructure.org/en): La insignia CII indica el nivel de cumplimiento de un proyecto con las «mejores prácticas para proyectos de código abierto» según lo definido por la Iniciativa de Infraestructura Central de la Fundación Linux, que se centra en la ciberseguridad en el software de código abierto. El objetivo del programa es alentar a los proyectos a producir un software mejor y más seguro, y permitir que otros determinen si un proyecto sigue las mejores prácticas.

Los consumidores de la insignia pueden evaluar rápidamente qué proyectos de código abierto siguen las mejores prácticas y, como resultado, es más probable que produzcan software seguro de mayor calidad.

## Implementación

Consulte la [documentación de la API de la CII](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md) para obtener más información.

### Visualizaciones

![](https://i.imgur.com/mSformz.png)

### Herramientas que proporcionan la métrica

Augur proporciona un ejemplo de implementación para la métrica Mejores prácticas de CII. Puede encontrar un ejemplo de métricas de CII en uso en http://augur.osshealth.io/repo/Zephyr-RTOS/zephyr/risk

### Estrategias de recopilación de datos

Consulte la [documentación de la API de la CII](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/api.md) para obtener más información.

De acuerdo con la [página de la Insignia de Mejores Prácticas de la CII](https://bestpractices.coreinfrastructure.org/en): los proyectos reciben la insignia de aprobación si cumplen con todos los criterios requeridos. El estado de cada criterio, para un proyecto determinado, puede ser «Cumplido», «No cumplido», «N/D» o «desconocido». Cada criterio se encuentra en una de las siguientes cuatro categorías: «MUST» (debe), «SHOULD» (debería), «SUGGESTED» (sugerido) o «FUTURE» (futuro). Para obtener una insignia, se deben cumplir todos los criterios MUST y MUST NOT, se deben cumplir todos los criterios SHOULD o bien se debe documentar la razón para no implementar el criterio, y todos los criterios SUGGESTED deben calificarse como cumplidos o no cumplidos. Si el proyecto cumple con los criterios adicionales, hay disponibles niveles de insignia avanzados de plata y oro.

## Referencias

- Sitio web de Insignia del CII: https://bestpractices.coreinfrastructure.org/en
- Augur: https://github.com/chaoss/augur




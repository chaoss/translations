# Factor elefante

Pregunta: ¿Cuál es la distribución del trabajo en la comunidad?


## Descripción

El número mínimo de empresas cuyos empleados realizan una definición parametrizable del porcentaje total de commits en un repositorio de software es el «factor elefante» de un proyecto. Por ejemplo, un filtro común es decir que el 50% de los commits los realizan `n empresas` y ese es el factor elefante. Se empezaría a sumar al porcentaje parametrizado utilizando las organizaciones más grandes que hacen contribuciones, y luego la siguiente más grande y así sucesivamente. Así, por ejemplo, un proyecto con 8 organizaciones contribuyentes, cada una de las cuales contribuyó con el 12,5% de los commits en un proyecto, si el factor elefante se parametriza al 50%, tendría un factor elefante de «4». Si una de esas organizaciones fuera responsable del 50% de los commits en el mismo escenario, entonces el factor elefante sería «1».

El Factor elefante proporciona una indicación fácil de consumir del número mínimo de empresas que realizan un determinado porcentaje (es decir, el 50%) del trabajo. El origen del término «factor elefante» no está claramente delineado en la literatura, aunque puede surgir de la identificación general de la sostenibilidad del software como un requisito crítico de software no funcional por parte de Venters et al (2014).


## Objetivos

Una empresa que evalúe productos de software de código abierto podría utilizar el factor elefante para comparar en qué medida un proyecto depende de un pequeño conjunto de contribuyentes corporativos. Los proyectos con bajos factores elefante son intuitivamente más vulnerables a las decisiones de una empresa que pasa en cascada por cualquier empresa que consuma esa herramienta. El filtro parametrizado debería ser razonablemente diferente para un proyecto al que contribuyen 1.000 organizaciones que para uno al que contribuyen, por ejemplo, 10. Con un cierto volumen de contribución organizativa, probablemente algo menos de 1.000 organizaciones, es probable que el factor elefante no sea una consideración central para la adquisición de programas informáticos porque los administradores razonables juzgarán que el proyecto no es vulnerable a las decisiones de un pequeño número de actores. Estos umbrales son muy contextuales.


## Implementación

La fórmula del factor elefante es un cálculo porcentual -será nuestro umbral- seguido de sumar las contribuciones de cada empresa ordenadas en orden decreciente hasta llegar al umbral.

Si tenemos 8 organizaciones y cada una de las cuales contribuye con el siguiente número de commits a un proyecto: `1000, 202, 90, 33, 332, 343, 42, 433`, entonces podemos determinar el factor elefante identificando primero el 50% del total de commits para todas las empresas.

**Resumen:** 50% de las contribuciones totales = `1.237,5`, por lo que el factor elefante es `2`.

**Solución completa:**
1. Organice los datos en orden descendente: `1000, 433, 343, 332, 202, 90, 42, 33`
2. Calcule el 50% del total:
   -  `(1.000 + 433 + 343 + 332 + 202 + 90 + 42 + 33) * 0,5 = 1.237,5`
3. Sumando las dos primeras empresas de nuestro ranking obtenemos `1.433`.
4. **Respuesta**: como `1.433 > 1.237,5`, más del 50% de las contribuciones las realizan solo `2` empresas, por lo que podemos decir que el `factor elefante = 2`.


### Filtros

* Tiempo: razonablemente, el factor elefante cambiará si se toma una instantánea de cualquier período de tiempo anterior, por lo que el factor elefante durante la vida útil de un producto puede tergiversar el nivel actual de diversidad organizativa respaldado por el proyecto.
* Grupo de repositorios: muchos proyectos de código abierto incluyen varios repositorios y, en algunos casos, el examen de todos los repositorios asociados con un proyecto determinado proporciona una imagen más completa del factor elefante.


### Herramientas que proporcionan la métrica

1. [Augur](https://github.com/chaoss/augur)
2. [GrimoireLab](https://chaoss.github.io/grimoirelab) proporciona esta métrica lista para usar, no como un número único sino como una visualización.
  - Vea un ejemplo de en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/Git).
  - Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/panels/git/).
  - Añada una visualización de muestra a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree un nuevo gráfico `circular`
    * Seleccione el índice `git`
    * Tamaño de la porción de las métricas: Agregación `Cantidad`
    * Segmentos divididos en cubos: Agregación `Términos`, Campo `author_org_name`, Ordenar por `métrica: Cantidad`, Orden `Descendente`, Tamaño `500`
  - Captura de pantalla de ejemplo: ![Captura de pantalla de GrimoireLab de la métrica Elephant_Factor](https://github.com/chaoss/wg-risk/blob/master/metrics/images/elephant_factor-GrimoireLab.png)


## Referencias

1. Colin C. Venters, Lydia Lau, Michael K. Griffiths, Violeta Holmes, Rupert R. Ward, Caroline Jay, Charlie E. Dibsdale y Jie Xu. 2014. Los ciegos y el elefante: hacia un marco de evaluación empírica para la sostenibilidad del software. Revista de software de investigación abierta 2, 1. https://doi.org/10.5334/jors.ao
2. http://philslade.blogspot.com/2015/07/what-is-elephant-factor.html
3. https://blog.bitergia.com/2016/06/07/landing-the-new-eclipse-open-analytics-dashboard/
4. https://www.stackalytics.com/

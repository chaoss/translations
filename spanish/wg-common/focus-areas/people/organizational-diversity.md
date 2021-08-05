# Diversidad organizacional

Pregunta: ¿Cuál es la diversidad organizacional de las contribuciones?

## Descripción

La diversidad organizacional expresa cuántas organizaciones diferentes participan en un proyecto y en qué medida están involucradas las diferentes organizaciones en comparación entre sí.

## Objetivos

* Obtener una lista de organizaciones que contribuyen a un proyecto.
* Ver el porcentaje de contribuciones de cada organización dentro de un período de tiempo definido.
* Ver el cambio de composición de las organizaciones dentro de un período de tiempo definido.
* Obtener una lista de las personas asociadas con cada organización.

## Implementación

* Recopile datos de fuentes de datos donde se producen las contribuciones.
* Identifique las afiliaciones de los contribuyentes para obtener una buena estimación de las organizaciones a las que pertenecen.
* Correlacione la información sobre las contribuciones, asignando cada una a la organización adecuada.
* Dependiendo de las necesidades del proyecto, es posible que desee considerar cuestiones como la forma de manejar varias direcciones de correo electrónico, cambios de afiliación a lo largo del tiempo o contratista vs. empleado.

### Herramientas que proporcionan la métrica

* [GrimoireLab](https://chaoss.github.io/grimoirelab) cuenta con métricas de diversidad organizacional listas para usar. [GrimoireLab SortingHat](https://github.com/chaoss/grimoirelab-sortinghat) gestiona identidades. La interfaz de usuario [GrimoireLab Hatstall](https://github.com/chaoss/grimoirelab-hatstall) permite corregir la afiliación organizacional de las personas e incluso registrar cambios de afiliación.
  * Vea un ejemplo de visualización en la [instancia CHAOSS de Bitergia Analytics](https://chaoss.biterg.io/app/kibana#/dashboard/Community-Structure-by-Organization).
  * Descargue e importe un panel de control listo para usar que contiene ejemplos para esta visualización de métricas de la [colección de paneles de GrimoireLab Sigils](https://chaoss.github.io/grimoirelab-sigils/panels/community-structure-by-organization/).
  * Añada una visualización de muestra a cualquier panel de GrimoreLab Kibiter siguiendo estas instrucciones:
    * Cree un nuevo gráfico Circular
      * Seleccione el índice `all_onion`
      * Tamaño de los segmentos de las métricas: Agregación `Suma`, Campo `contribuciones`, Etiqueta personalizada `Contribuciones`
      * Segmentos divididos en cubos: Agregación `Términos`, Campo `autor_o_nombre`, Ordenar por `métrica: Contribuciones`, Orden `Descendente`, Tamaño `500`, Etiqueta personalizada `Organización`
    * Captura de pantalla de ejemplo

    ![Gráfico circular de diversidad organizacional](images/piechart.png)

* [LF Analytics](https://lfanalytics.io) proporciona métricas de diversidad organizacional en la vista principal para commits, incidencias presentadas y canales de comunicación (soporte actual para Slack y groups.io)

![Vista de diversidad organizacional](images/lfanalytics-orgdiversity.png)



### Estrategias de recopilación de datos

**Cualitativa**

* Huella de una organización en un proyecto o ecosistema
* Influencia de una organización en un proyecto o ecosistema
* Diversidad de afiliaciones en las estructuras de gobierno.

**Cuantitativa**

* % de commits por cada organización
* % de fusiones/revisiones de cada organización
* % de cualquier tipo de contribuyentes de cada organización
* % de líneas de código aportadas por cada organización
* % de incidencias presentadas por cada organización
* [Organizaciones contribuyentes](https://github.com/chaoss/metrics/blob/master/activity-metrics/contributing-organizations.md): ¿Cuál es el número de organizaciones contribuyentes?
* [Nuevas organizaciones contribuyentes](https://github.com/chaoss/metrics/blob/master/activity-metrics/new-contributing-organizations.md): ¿Cuál es el número de nuevas organizaciones contribuyentes?
* Nuevas organizaciones contribuyentes: nuevas organizaciones que contribuyen al proyecto a lo largo del tiempo.
* Número de organizaciones contribuyentes: número de organizaciones que participan en el proyecto a lo largo del tiempo.
* Factor elefante: si el 50% de los miembros de la comunidad están empleados por la misma empresa, hay un elefante en la habitación. Formalmente: el número mínimo de empresas cuyos empleados realizan el 50% de los commits
* [Diversidad de afiliaciones](https://github.com/chaoss/metrics/blob/master/activity-metrics/contributor-diversity.md): proporción de contribuyentes de una sola empresa sobre todos los contribuyentes. También se describe como: Mantenedores de diferentes empresas. Diversidad de afiliación de contribuyentes.
* En proyectos con el concepto de propiedad del código, % de propietarios de código afiliados a cada organización ponderados por la importancia/tamaño/LoC del código que poseen y el número de copropietarios.

## Referencias

* Posibles implementaciones y referencias:
  * [https://bitergia.gitlab.io/panel-collections/open_source_program_office/organizational-diversity.html](https://bitergia.gitlab.io/panel-collections/open_source_program_office/organizational-diversity.html)
  * [Página de entrada del panel de Kata Containers](https://katacontainers.biterg.io) (parte inferior de esta)
  * [Augur](https://github.com/chaoss/augur)

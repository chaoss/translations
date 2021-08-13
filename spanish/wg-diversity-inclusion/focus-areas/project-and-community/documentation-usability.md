# Usabilidad de la documentación

Pregunta: ¿Cuál es la usabilidad de la documentación desde la perspectiva del contenido y la estructura?


## Descripción

La usabilidad de la documentación aborda el papel fundamental de la documentación de un proyecto de código abierto asegurándose de que diferentes tipos de usuarios puedan comprenderla. La usabilidad de la documentación contiene cuestiones de estructura, contenido, jerga y legibilidad con el objetivo de fomentar la comprensión de la audiencia más amplia de contribuyentes al proyecto.


## Objetivos
* **Jerga técnica**: la documentación utiliza un nivel apropiado de jerga técnica y proporciona una explicación de la terminología según sea necesario para garantizar que la documentación sea comprensible para un contribuyente del proyecto de nivel principiante.
* **Claridad estructural**: la documentación es fácil de seguir y de comprender.
* **Legibilidad**: la documentación utiliza un lenguaje claro y conciso, con palabras de significado común y oraciones cortas, para garantizar que la documentación sea comprensible para las personas para quienes el idioma no es nativo o para quienes no siguen convenciones taquigráficas o patrones de inferencia similares.
* **Lenguaje inclusivo**: la documentación evita el lenguaje no inclusivo (por ejemplo, lenguaje «brogrammer» o lenguaje excluyente/despectivo).
* **Diversidad de idiomas**: la documentación está disponible en una lengua vernácula común para el público objetivo y en diferentes idiomas.
* **Diversidad de tiempo/atención**: la documentación incluye a las personas que tienen diferencias en el tiempo que pueden dedicar a la documentación, ya sea leyendo o configurando/ejecutando comandos. Vale la pena considerar a las personas que son responsables del cuidado de niños u otras responsabilidades de cuidado que pueden desviar su atención de sus pantallas en cualquier momento.

## Implementación

### Estrategias de recopilación de datos

* Entreviste a los recién llegados para determinar cómo la documentación ayudó al contribuyente a (a) comprender el proceso de contribución y/o (b) completar la tarea. Ejemplos de preguntas para la entrevista:
  * Describa su experiencia con el uso de la documentación para comprender el proceso de contribución.
  * Describa su experiencia con el uso de la documentación para resolver una duda sobre cómo trabajar en la comunidad.
  * Describa su experiencia con el uso de la documentación para comprender cómo ayudar en los esfuerzos de divulgación.
  * ¿Cómo de cómodo se sintió con la cantidad de términos técnicos presentes aquí? (adaptar a la encuesta usando escala Likert [1-5])
  * ¿Hubo algún término o idioma que no entendió?
  * ¿Qué sugerencias tiene para mejorar las políticas, los procesos o las directrices del proyecto disponibles para los nuevos contribuyentes?
  * Después de la entrevista, la comunidad puede realizar un seguimiento de las respuestas a cada pregunta como `Experiencia positiva`, `Experiencia negativa` o `Experiencia neutral` e informar mes a mes para ver la mejora con el tiempo.
* Haga preguntas sobre la legibilidad y la capacidad de escaneo, tales como: ¿La documentación utiliza construcciones organizativas, como:
  * Encabezados
  * Bloques de texto y código
  * Viñetas versus párrafos
  * Anclas
* Tutorial con usuarios previstos de la documentación. Observe cómo interactúan y usan la documentación y dónde se atascan. Puede ser una sesión de videoconferencia donde el usuario de la documentación comparte su pantalla.
* Pida a los usuarios de la documentación que escriban un [registro de fricción](https://devrel.net/developer-experience/an-introduction-to-friction-logging) y describan los problemas que tuvieron con la documentación. Esto proporciona casos de uso concretos para que los editores de la documentación comprendan cómo mejorar la documentación para el usuario específico.
* Considere si hay diferentes versiones de la documentación disponibles para diferentes públicos. Por ejemplo, una versión ligera y una versión muy detallada de la documentación.



## Recursos

* [Directrices de accesibilidad al contenido web del W3C](https://www.w3.org/WAI/standards-guidelines/wcag/)
* [Lista de herramientas de evaluación de accesibilidad web del W3C](https://www.w3.org/WAI/ER/tools/)
* [Algunas pruebas rápidas para evaluar la accesibilidad web](https://a11yproject.com/#Quick-tests)
* [Un grupo que se especializa en Accesibilidad](https://knowbility.org/services/document-accessibility/)
* [Reflexiones sobre las métricas de accesibilidad](https://www.boia.org/blog/3-times-accessibility-and-disability-stats-matter-and-3-times-they-dont)
* [GNOME sobre accesibilidad ](https://wiki.gnome.org/Accessibility)
* [Lista de directrices de accesibilidad de Paypal](http://paypal.github.io/a11y/)
* [La Iniciativa de Infraestructura Central: Insignia de Mejores Prácticas](https://bestpractices.coreinfrastructure.org/en)
* [Derribando barreras a la contribución de Kubernetes para individuos neurodivergentes](https://static.sched.com/hosted_files/kcsna2019/05/Breaking%20Down%20Barriers%20to%20Kubernetes%20Contribution%20for%20Neurodivergent%20Individuals%20%282%29.pdf)
* [`documentation_basics`](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md#documentation_basics)
* [`documentation_interface`](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md#documentation_interface)
* [Registro de fricción](https://devrel.net/developer-experience/an-introduction-to-friction-logging)
* [Stanford: prueba del lector de pantalla](https://soap.stanford.edu/tips/screen-reader-testing)

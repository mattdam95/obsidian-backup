# Introducción a Buenas Prácticas en Desarrollo Frontend

El desarrollo front-end implica la creación de los aspectos visuales e interactivos de un sitio web o una aplicación que los usuarios ven e interactúan. Asegurarse de que los templates, estilos y código front-end estén optimizados, que se puedan mantener y sigan los estándares de la industria es esencial para crear una experiencia de usuario ideal.

Para esto vamos a abarcar varios puntos generales que vamos a ir desarrollando más adelante.

- **Uso de etiquetas HTML semánticas**: Ayuda a mejorar la accesibilidad y la legibilidad del código. Por ejemplo, en lugar de usar una etiqueta `div` para representar un encabezado, puede usar la etiqueta `header`. Esto le da más significado al contenido y hace que sea más fácil de interpretar para los lectores de pantalla.

- **Uso de Preprocesadores de CSS**: Como SASS o LESS, permiten el uso de funciones y técnicas avanzadas en CSS que no están disponibles en Vanilla CSS. Por ejemplo, puede usar variables, combinaciones y reglas anidadas para hacer que los estilos estén más organizados y fáciles de mantener.

- **Usar CDN para js, CSS e imágenes**: Una CDN es una red de servidores que entregan contenido. El uso de una CDN puede mejorar el rendimiento al reducir la distancia entre el usuario y el servidor. Además, permite el almacenamiento en caché de los archivos.

- **Optimizar imágenes y otros recursos**: La optimización de imágenes y otros recursos puede ayudar a mejorar el rendimiento y la velocidad del sitio web. Esto se puede hacer a través de técnicas como la compresión de imágenes, el uso de formatos de archivo de imagen apropiados y la carga diferida de imágenes.

- **Gráficos vectoriales**: Los gráficos vectoriales son imágenes definidas por puntos y rutas, en lugar de píxeles, y se pueden escalar a cualquier tamaño sin perder calidad. Esto puede hacer que su uso sea más eficiente, especialmente para gráficos que se mostrarán en diferentes tamaños.

## Principios de Accesibilidad

Cumplir con los principios de accesibilidad ayuda a que el sitio web sea más inclusivo y más fácil de usar para personas con discapacidades. Esto se puede lograr a través de técnicas como proporcionar texto alternativo para las imágenes, usar una estructura de encabezado adecuada y agregar etiquetas de formulario adecuadas.

## Optimización en JavaScript - Typescript

JavaScript es un lenguaje de programación potente y flexible, pero también puede requerir muchos recursos. Por lo tanto, es importante optimizar su código JavaScript para garantizar que se ejecute de manera eficiente y no afecte el rendimiento general de su sitio web o aplicación.

Aquí hay algunos consejos para optimizar el rendimiento de JavaScript:

- **Minimizar el código**: Eliminar espacios en blanco, comentarios y otros caracteres innecesarios ayuda a reducir el tamaño de los archivos y mejorar los tiempos de carga.

- **Compilador de JavaScript**: Un compilador de JavaScript, como Babel o TypeScript, ayuda a optimizar el código al convertirlo a un formato más eficiente.

- **Evitar bloquear el subproceso principal**: El subproceso principal es responsable de manejar las interacciones del usuario y mostrar la página, por lo que es importante evitar bloquearlo con tareas de ejecución prolongada o que consumen muchos recursos. En su lugar, considere usar funciones asincrónicas para descargar estas tareas a otros subprocesos.

- **División de código**: Le permite cargar el JavaScript en fragmentos más pequeños que se pueden cargar a pedido. Esto puede mejorar el rendimiento al reducir la cantidad de código que debe cargarse y analizarse inicialmente.

- **Lazy load**: Permite retrasar la carga de contenido hasta que sea necesario. Esto puede mejorar el rendimiento al reducir la cantidad de datos que deben cargarse inicialmente. Angular provee muchas herramientas para esto.

- **Almacenar en caché**: Permite el almacenamiento de datos en el navegador para que puedan reutilizarse sin necesidad de recuperarlos del servidor nuevamente. Esto puede mejorar el rendimiento al reducir la cantidad de solicitudes de red que se deben realizar.

- **Linting**: El uso de herramientas para el linteo de errores como ESLint, verifica el código en busca de errores y sugiere mejoras, esto ayuda a garantizar que el código sea consistente y siga las mejores prácticas.

## Generalización de Formatos

- **Commits**: Es fundamental seleccionar una convención para realizar los commits en los proyectos. Esto garantiza que todos los desarrolladores comprendan los cambios realizados y se mantenga consistencia.

- **Versionado**: Asimismo, resulta crucial establecer una convención para el versionado de las aplicaciones desarrolladas. Esto asegura una gestión ordenada de las versiones de las aplicaciones y facilita la comunicación entre los equipos de desarrollo.

## Conclusión

El desarrollo front-end implica una amplia gama de prácticas y técnicas que pueden ayudar a mejorar el rendimiento y la experiencia del usuario de un sitio web.